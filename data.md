const crypto = require('crypto');

function b64url(input) {
  return Buffer.from(input)
    .toString('base64')
    .replace(/\+/g, '-')
    .replace(/\//g, '_')
    .replace(/=+$/, '');
}

function signJwt(payload, secret) {
  const header = { alg: 'HS256', typ: 'JWT' };
  const headerB64 = b64url(JSON.stringify(header));
  const payloadB64 = b64url(JSON.stringify(payload));
  const data = `${headerB64}.${payloadB64}`;
  const signature = crypto.createHmac('sha256', secret).update(data).digest();
  const sigB64 = signature.toString('base64').replace(/\+/g, '-').replace(/\//g, '_').replace(/=+$/, '');
  return `${data}.${sigB64}`;
}

const jwtSecret = crypto.randomBytes(32).toString('hex'); // 64 char hex
const postgresPassword = crypto.randomBytes(24).toString('base64').replace(/[/+=]/g, '').slice(0, 32);
const dashboardPassword = crypto.randomBytes(18).toString('base64').replace(/[/+=]/g, '').slice(0, 24);
const secretKeyBase = crypto.randomBytes(48).toString('hex');
const vaultEncKey = crypto.randomBytes(24).toString('base64').replace(/[/+=]/g, '').slice(0, 32);

const now = Math.floor(Date.now() / 1000);
const tenYears = now + 10 * 365 * 24 * 60 * 60;

const anonKey = signJwt({ role: 'anon', iss: 'supabase', iat: now, exp: tenYears }, jwtSecret);
const serviceRoleKey = signJwt({ role: 'service_role', iss: 'supabase', iat: now, exp: tenYears }, jwtSecret);

console.log('JWT_SECRET=' + jwtSecret);
console.log('POSTGRES_PASSWORD=' + postgresPassword);
console.log('DASHBOARD_USERNAME=admin');
console.log('DASHBOARD_PASSWORD=' + dashboardPassword);
console.log('SECRET_KEY_BASE=' + secretKeyBase);
console.log('VAULT_ENC_KEY=' + vaultEncKey);
console.log('ANON_KEY=' + anonKey);
console.log('SERVICE_ROLE_KEY=' + serviceRoleKey);
