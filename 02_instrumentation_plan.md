# OrangeHRM Instrumentation & Observation Plan

## Observation Checkpoints

### 1. Frontend Console Monitoring
**What to observe:**
- Console errors, warnings, and info messages
- Missing autocomplete attributes (password fields)
- Slow network warnings affecting font loading
- WebGL fallback warnings affecting performance

**Tools:** Browser DevTools Console, Playwright console monitoring

### 2. Network Request Analysis
**What to observe:**
- API response times (all requests returning 200/302/304 as expected)
- Failed requests (5xx errors)
- Authentication flow (POST to /auth/validate → 302 redirect)
- API endpoint patterns:
  - `/api/v2/pim/employees` for employee data
  - `/api/v2/leave/employees/leave-requests` for leave data
  - `/api/v2/admin/users` for user management
  - `/api/v2/dashboard/*` for dashboard widgets

**Tools:** Browser DevTools Network tab, Playwright network monitoring

### 3. Page Load Performance
**What to observe:**
- Initial page load times
- Resource loading (CSS, JS, fonts, images)
- Page transition speeds between modules
- Module redirects (PIM/Leave/Admin all redirect to specific sub-pages)

### 4. Frontend Error Patterns
**Current Issues Detected:**
- Password field missing autocomplete="current-password" attribute
- Slow network font loading issues
- YouTube embed causing additional network calls on dashboard

### 5. API Response Monitoring
**Key Endpoints to Watch:**
- Authentication: `POST /auth/validate`
- Employee search: `GET /api/v2/pim/employees`
- Leave requests: `GET /api/v2/leave/employees/leave-requests`
- User management: `GET /api/v2/admin/users`
- Dashboard data: Multiple `/api/v2/dashboard/*` endpoints

### 6. Data Quality Observations
**Employee Data Issues Noted:**
- Inconsistent employee ID formats (numeric, alphanumeric, with/without leading zeros)
- Mix of test data and realistic names
- Some employees missing job titles, employment status, sub-units
- Special characters and long strings in employee names (test data pollution)

### 7. Security Observations
**Items to Monitor:**
- HTTPS usage (✓ All requests over HTTPS)
- Session management (login flow working correctly)
- Password field security attributes
- CSRF token handling in forms

## Instrumentation Strategy for NTSUGKI Testing

### For Negative & Noise (N) Testing:
- Monitor API responses to malformed requests
- Watch for XSS/injection attempt handling
- Observe error handling for edge case inputs

### For Targeted Exploration (T) Testing:
- Track page performance under different conditions
- Monitor session persistence across browser actions
- Observe mobile responsiveness indicators

### For Simulate Real Users (S) Testing:
- Monitor multi-tab behavior and session conflicts
- Track workflow completion rates and drop-off points
- Observe concurrent user action handling

### For Utilize Chaos (U) Testing:
- Monitor network timeout handling
- Track error recovery mechanisms
- Observe graceful degradation under stress