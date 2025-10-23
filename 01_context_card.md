# OrangeHRM Testing Context Card

## Context Card
OrangeHRM is a comprehensive Human Resource Management System that manages employee information, leave requests, recruitment, performance tracking, and administrative functions. The application serves as a central hub for HR operations where administrators can manage system users, employees can apply for leave, and managers can approve/reject requests. The most critical functionality centers around employee data management, leave workflow processing, and user access control, as these represent the core business operations that directly impact payroll, compliance, and operational efficiency.

## Top 3 Critical Flows

### 1. Employee Management Flow (PIM Module)
**Path**: PIM → Employee List → Add/Edit Employee → Personal Details
- **Business Impact**: Core employee data that feeds into payroll, benefits, and compliance reporting
- **Critical Operations**: Create employee, update personal information, employment status changes
- **Dependencies**: Used by Leave, Performance, and Admin modules

### 2. Leave Request & Approval Workflow
**Path**: Leave → Apply → Manager Review → Approve/Reject → Employee Notification
- **Business Impact**: Directly affects staffing, payroll calculations, and compliance with labor laws
- **Critical Operations**: Apply for leave, approval workflow, leave balance calculations
- **Dependencies**: Requires employee data from PIM, affects Time tracking

### 3. User Access & Security Management (Admin Module)
**Path**: Admin → User Management → Create/Edit System Users → Role Assignment
- **Business Impact**: Controls system security, data access, and role-based permissions
- **Critical Operations**: User creation, role assignment, password management, access control
- **Dependencies**: Foundational for all other modules and security compliance

## Key Observations from Initial Exploration
- Application has 179+ employee records with mixed data quality (some test data, some realistic names)
- Leave module shows pending approvals requiring manager action
- Console shows "Slow network" warnings and autocomplete attribute suggestions
- Multi-level navigation with module-based architecture
- Role-based access control system in place