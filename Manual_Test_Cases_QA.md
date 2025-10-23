# OrangeHRM Manual Test Cases for QA Team

## Test Documentation Overview
**Purpose**: Manual test cases for QA team execution  
**System Under Test**: OrangeHRM v5.7 Demo System  
**Test Environment**: https://opensource-demo.orangehrmlive.com/  
**Date Created**: October 23, 2025  
**Test Coverage**: Critical business flows and security scenarios

---

## Test Case 1: Employee Management - Add New Employee

**Test Case ID**: TC_EMP_001  
**Priority**: High  
**Category**: Functional - Employee Management  
**Estimated Time**: 5 minutes

### Test Objective
Verify that HR managers can successfully create new employee records with complete information.

### Prerequisites
- User has Admin or HR Manager privileges
- System is accessible and user is logged in

### Test Data
- Employee First Name: [Use any realistic name]
- Employee Last Name: [Use any realistic surname]  
- Employee ID: [Leave blank for auto-generation]
- Middle Name: [Optional]

### Test Steps

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Login to OrangeHRM with Admin credentials (Username: Admin, Password: admin123) | Login successful, Dashboard displays |
| 2 | Navigate to PIM module from left sidebar | PIM module opens, Employee List displays |
| 3 | Click "Add Employee" from top navigation | Add Employee form opens |
| 4 | Enter First Name in the "First Name" field | Text entered successfully |
| 5 | Enter Last Name in the "Last Name" field | Text entered successfully |
| 6 | Leave Employee ID field blank (for auto-generation) | Field remains empty |
| 7 | Click "Save" button | Success message appears: "Successfully Saved" |
| 8 | Verify employee appears in Employee List | New employee visible in list with auto-generated ID |
| 9 | Click on the new employee record | Employee details page opens correctly |

### Expected Results
- Employee record created successfully
- Auto-generated Employee ID assigned
- Success notification displayed
- Employee visible in search results
- All data saved correctly

### Pass/Fail Criteria
**PASS**: All steps complete successfully, employee created and visible  
**FAIL**: Any step fails, error messages appear, or data not saved

---

## Test Case 2: Leave Management - Apply for Leave

**Test Case ID**: TC_LEAVE_001  
**Priority**: High  
**Category**: Functional - Leave Management  
**Estimated Time**: 7 minutes

### Test Objective
Verify that employees can successfully apply for leave with proper workflow validation.

### Prerequisites
- Employee user account exists with leave privileges
- Leave types are configured in the system

### Test Data
- Leave Type: Annual Leave (or available option)
- From Date: [Next Monday]
- To Date: [Next Tuesday] 
- Comment: "Family vacation"

### Test Steps

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Login with employee credentials | Dashboard displays with user context |
| 2 | Navigate to Leave → Apply Leave | Apply Leave form opens |
| 3 | Select "Annual Leave" from Leave Type dropdown | Leave type selected, balance may display |
| 4 | Click "From Date" calendar icon | Date picker opens |
| 5 | Select next Monday as From Date | Date selected and field populated |
| 6 | Click "To Date" calendar icon | Date picker opens |
| 7 | Select next Tuesday as To Date | Date selected and field populated |
| 8 | Enter "Family vacation" in Comments field | Comment text entered |
| 9 | Click "Apply" button | Success message appears: "Successfully Submitted" |
| 10 | Navigate to Leave → My Leave | Leave request visible in list with "Pending Approval" status |

### Expected Results
- Leave application submitted successfully
- Confirmation message displayed
- Leave request appears in "My Leave" list
- Status shows "Pending Approval"
- All entered data preserved correctly

### Pass/Fail Criteria
**PASS**: Leave application submitted and visible in pending status  
**FAIL**: Submission fails, error messages appear, or data not saved

---

## Test Case 3: User Account Management - Create System User

**Test Case ID**: TC_USER_001  
**Priority**: High  
**Category**: Functional - User Management  
**Estimated Time**: 6 minutes

### Test Objective
Verify that administrators can create new system user accounts with proper role assignment.

### Prerequisites
- Admin privileges required
- Employee record exists to link to user account
- User roles are configured

### Test Data
- User Role: ESS (Employee Self Service)
- Employee Name: [Select existing employee]
- Username: [Unique username]
- Password: [Strong password]

### Test Steps

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Login as Admin user | Admin dashboard displays |
| 2 | Navigate to Admin → User Management → Users | System Users list displays |
| 3 | Click "Add" button | Add User form opens |
| 4 | Select "ESS" from User Role dropdown | Role selected |
| 5 | Type employee name in Employee Name field | Autocomplete suggestions appear |
| 6 | Select an employee from suggestions | Employee selected and linked |
| 7 | Enter unique username in Username field | Username entered |
| 8 | Enter password in Password field | Password masked/hidden |
| 9 | Confirm password in Confirm Password field | Password confirmation entered |
| 10 | Click "Save" button | Success message: "Successfully Saved" |
| 11 | Verify user appears in Users list | New user visible with ESS role |
| 12 | Test login with new credentials | Login successful with appropriate permissions |

### Expected Results
- User account created successfully
- Employee linkage established
- Appropriate role permissions applied
- New credentials work for login
- User visible in system users list

### Pass/Fail Criteria
**PASS**: User created, linked to employee, and login successful  
**FAIL**: Creation fails, linkage incorrect, or login doesn't work

---

## Test Case 4: Security Testing - SQL Injection Protection

**Test Case ID**: TC_SEC_001  
**Priority**: Critical  
**Category**: Security - Input Validation  
**Estimated Time**: 10 minutes

### Test Objective
Verify that the system properly protects against SQL injection attacks.

### Prerequisites
- Access to login form and other input fields
- Understanding of SQL injection techniques

### Test Data - Malicious SQL Payloads
- `' OR '1'='1' --`
- `'; DROP TABLE users; --`
- `' UNION SELECT * FROM users --`
- `admin'--`

### Test Steps

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Navigate to login page | Login form displays |
| 2 | Enter `' OR '1'='1' --` in Username field | Malicious input entered |
| 3 | Enter any text in Password field | Password entered |
| 4 | Click Login button | Login fails, error message or redirect |
| 5 | Check browser developer tools for errors | No SQL errors visible |
| 6 | Navigate to Employee search | Search form opens |
| 7 | Enter `'; DROP TABLE users; --` in search field | Malicious payload entered |
| 8 | Click Search button | Search fails gracefully or returns no results |
| 9 | Verify system still functions normally | No system damage or data exposure |
| 10 | Test additional input fields with SQL payloads | All inputs properly sanitized |

### Expected Results
- All SQL injection attempts blocked
- No unauthorized access granted
- No SQL errors exposed to user
- System remains stable and functional
- Proper error handling without information disclosure

### Pass/Fail Criteria
**PASS**: All injection attempts blocked, no system compromise  
**FAIL**: Injection succeeds, unauthorized access, or system errors

---

## Test Case 5: Performance Testing - Page Load Times

**Test Case ID**: TC_PERF_001  
**Priority**: Medium  
**Category**: Performance - Load Times  
**Estimated Time**: 15 minutes

### Test Objective
Verify that all major pages load within acceptable time limits.

### Prerequisites
- Stable internet connection
- Browser developer tools available
- System under normal load

### Performance Benchmarks
- Login Page: < 3 seconds
- Dashboard: < 5 seconds
- Employee List: < 7 seconds
- Forms: < 4 seconds

### Test Steps

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Open browser developer tools (F12) | Developer tools open |
| 2 | Navigate to OrangeHRM login page | Page loads, note time in Network tab |
| 3 | Record page load time | Load time < 3 seconds |
| 4 | Login with valid credentials | Dashboard loads, note time |
| 5 | Record dashboard load time | Load time < 5 seconds |
| 6 | Navigate to PIM → Employee List | Employee list loads |
| 7 | Record employee list load time | Load time < 7 seconds |
| 8 | Open Add Employee form | Form loads quickly |
| 9 | Record form load time | Load time < 4 seconds |
| 10 | Test navigation between modules | All modules load within limits |

### Expected Results
- All pages load within specified time limits
- No unusually long delays
- Smooth navigation between modules
- Responsive user interface

### Pass/Fail Criteria
**PASS**: All load times within benchmarks  
**FAIL**: Any page exceeds time limits consistently

---

## Test Case 6: Multi-Tab Session Management

**Test Case ID**: TC_UX_001  
**Priority**: Medium  
**Category**: User Experience - Session Handling  
**Estimated Time**: 8 minutes

### Test Objective
Verify that the system properly handles multiple browser tabs and maintains session integrity.

### Prerequisites
- User logged into the system
- Modern browser with tab support

### Test Steps

| Step | Action | Expected Result |
|------|--------|-----------------|
| 1 | Login to OrangeHRM in first tab | Session established |
| 2 | Navigate to PIM → Employee List | Employee list displays |
| 3 | Right-click on an employee and "Open in new tab" | New tab opens with employee details |
| 4 | In new tab, edit employee information | Changes can be made |
| 5 | Save changes in the new tab | Success message appears |
| 6 | Switch back to first tab (Employee List) | List still displays correctly |
| 7 | Refresh the first tab | Updated information reflects |
| 8 | Open third tab with same OrangeHRM site | Session maintained across tabs |
| 9 | Close one tab and continue working in others | Other tabs remain functional |
| 10 | Logout from one tab | All tabs logged out (if session shared) |

### Expected Results
- Session maintained across multiple tabs
- Data consistency between tabs
- Changes in one tab reflected in others
- No session conflicts or errors
- Proper logout behavior

### Pass/Fail Criteria
**PASS**: Multi-tab functionality works correctly  
**FAIL**: Session conflicts, data loss, or tab errors

---

## Test Execution Notes for QA Team

### General Testing Guidelines

1. **Test Data Management**
   - Use realistic test data
   - Clean up test data after execution
   - Don't use production-like sensitive information

2. **Browser Compatibility**
   - Test on Chrome, Firefox, Safari, Edge
   - Verify responsive design on different screen sizes
   - Check mobile browser compatibility

3. **Error Documentation**
   - Screenshot any errors encountered
   - Note exact error messages
   - Record browser console errors
   - Document steps to reproduce

4. **Environment Considerations**
   - Demo system may have limited data
   - Some features might be restricted
   - Performance may vary based on server load

### Bug Reporting Template

When logging defects, include:
- **Test Case ID** being executed
- **Environment details** (browser, OS, screen size)
- **Steps to reproduce** the issue
- **Expected vs Actual results**
- **Screenshots** or screen recordings
- **Severity and Priority** assessment
- **Workaround** if available

### Test Completion Checklist

- [ ] All test cases executed
- [ ] Results documented (Pass/Fail)
- [ ] Defects logged with proper details
- [ ] Test data cleaned up
- [ ] Test execution summary completed
- [ ] Stakeholders notified of results

---

**END OF MANUAL TEST CASES DOCUMENT**

*For questions or clarifications about these test cases, contact the Test Team Lead.*