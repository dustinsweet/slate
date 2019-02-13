# Users

## The User Object
> **Example**

```json
{
  "id": 317044,
  "first_name": "Bob",
  "last_name": "Jones",
  "group_id": 6908,
  "active": true,
  "employee_number": 10,
  "salaried": false,
  "exempt": false,
  "username": "bjones",
  "email": "bob_jones@anymail.com",
  "email_verified": false,
  "payroll_id": "SC010",
  "mobile_number": "2085551234",
  "hire_date": "2018-07-02",
  "term_date": "0000-00-00",
  "last_modified": "2019-02-09T17:59:06+00:00",
  "last_active": "2019-02-09T18:45:39+00:00",
  "created": "2018-10-04T02:25:38+00:00",
  "client_url": "spudsfunpark",
  "company_name": "Spuds Fun Park",
  "profile_image_url": "https://www.gravatar.com/avatar/6be49c2065c016dcdfcd26d1da111e9f",
  "pto_balances": {
    "2913946": 0,
    "2913948": 0,
    "2913950": 0
  },
  "submitted_to": "2000-01-01",
  "approved_to": "2000-01-01",
  "manager_of_group_ids": [],
  "require_password_change": false,
  "pay_rate": 8.26,
  "pay_interval": "hour",
  "permissions": {
    "admin": false,
    "mobile": true,
    "status_box": false,
    "reports": false,
    "manage_timesheets": false,
    "manage_authorization": false,
    "manage_users": false,
    "manage_my_timesheets": false,
    "manage_jobcodes": false,
    "pin_login": true,
    "approve_timesheets": false,
    "manage_schedules": false,
    "external_access": false,
    "manage_my_schedule": false,
    "manage_company_schedules": false,
    "view_company_schedules": false,
    "view_group_schedules": false,
    "manage_no_schedules": false,
    "view_my_schedules": false
  },
  "customfields": ""
}
```

Within TSheets, the `User` (aka "employee") refers to anyone on your account, including yourself, your employees, managers, administrators, and vendors.  Time can be tracked against any user.  The API provides methods to _Create_, _Read_, and _Update_ users and their permissions.  To archive a user, set the `active` property _false_.

|                |             |             |
| -------------: | :---------: | ----------- |
| **id**<br/>read-only | _Int_ | Unique identifier of this user. |
| **first_name**<br/>read-write | _String_ | The user's given name. |
| **last_name**<br/>read-write | _String_ | The user's surname. |
| **group_id**<br/>read-write | _Int_ | Id of the group this user belongs to. |
| **active**<br/>read-write | _Boolean_ | If false, this user is considered archived. |
| **employee_number**<br/>read-write | _Int_ | Unique number associated with this user, for external use. |
| **salaried**<br/>read-write | _Boolean_ | Indicates whether or not the user is salaried. |
| **exempt**<br/>read-write | _Boolean_ | Indicates whether or not the user is eligible for overtime pay. |
| **username**<br/>read-write | _String_ | Username associated with this user. |
| **email**<br/>read-write | _String_ | Email address associated with this user. |
| **email_verified**<br/>read-write | _Boolean_ | Indicates whether or not the email address has been confirmed by the user. |
| **payroll_id**<br/>read-write | _String_ | Unique company wide string associated with this user. Usually used for linking with external systems. |
| **hire_date**<br/>read-write | _String_ |  Date on which this user was hired (`YYYY-MM-DD` format).
| **term_date**<br/>read-write |  _String_ | Date on which this user was terminated (`YYYY-MM-DD` format).
| **last_modified**<br/>read-only | _String_ | Date/time when this user was last modified, in ISO 8601 format (`YYYY-MM-DDThh:mm:ss±hh:mm`).|
| **last_active**<br/>read-only | _String_ | Date/time when this user last performed any action, in ISO 8601 format (`YYYY-MM-DDThh:mm:ss±hh:mm`). |
| **created**<br/>read-only | _String_ | Date/time when this user was created, in ISO 8601 format (`YYYY-MM-DDThh:mm:ss±hh:mm`). |
| **client_url**<br/>read-only | _String_ |  Client account url identifier associated with this user. |
| **company_name**<br/>read-only | _String_ | Client account name identifier associated with the user. |
| **profile_image_url**<br/>read-only | _String_ | Url identifier associated with this user's profile image. |
| **mobile_number**<br/>read-write |  _String_ | Mobile phone number associated with this user. |
| **pto_balances**<br/>read-only | _Object_ | List of jobcode identifiers and their respective PTO balances for this user (in seconds). Jobcode information |for PTO Jobcodes will be supplied in `supplemental_data`. |
| **submitted_to**<br/>read-write | _String_ | The latest date this user has submitted timesheets up to (`YYYY-MM-DD` format). |
| **approved_to**<br/>read-write |  _String_ | The latest date this user has had timesheets approved to (`YYYY-MM-DD` format). |
| **manager_of_group_ids**<br/>read-only | _Int[]_ | The group ids that this user manages. |
| **require_password_change**<br/>read-write | _Boolean_ | If true, this user will be required to change their password on their next login. |
| **password**<br/>write-only | _String_ | May only be set when editing the currently authenticated user (i.e. you may only edit your own password). |
| **login_pin**<br/>write-only | _Int_ | Used for logging into a Kiosk or similar. |
| **pay_rate**<br/>read-only | _Float_ | The rate of pay associated with this user. |
| **pay_interval**<br/>read-only | _String_ | The timeframe to which this user's pay rate applies, either `hour` or `year` |
| **permissions**<br/>read-write | _Object_ | The [permission settings](#user-permissions) that apply to this user. |
| **customfields**<br/>read-write | _Object_ | [Customfield](#the-custom-field-object) items that are associated with the user. |

### User Permissions
The rights assignable to an individual user. All properties are _read-write_, and of type _Boolean_.

| Permission     | Default     | Description |
| -------------  | :---------: | ----------- |
| **admin** | false | Administrator, can perform any changes on the account. |
| **mobile** | true | Allowed to use mobile devices to record time. |
| **status_box** | false | Able to view the list of users currently working for the company. |
| **reports** | false | Able to run/view all reports for the company. |
| **manage_timesheets** | false | Able to create/edit/delete timesheets for anyone in the company. |
| **manage_authorization** | false | Able to manage computer authorization for the company. |
| **manage_users** | false | Able to create/edit/delete users, groups, and managers for the entire company. |
| **manage_my_timesheets** | false | Able to completely manage own timesheets. |
| **manage_jobcodes** | false | Able to create/edit/delete jobcodes and custom field items for the entire company. |
| **pin_login** | false | Able to login to apps via PIN. |
| **approve_timesheets** | false | Able to run approval reports and approve time for all employees. |
| **manage_schedules** | false | Able to create/edit/delete events within the schedule for the groups that the user can manage. |
| **manage_my_schedule** | false | Able to create/edit/delete events within the schedule for only themselves. |
| **manage_company_schedules** | false | Able to create/edit/delete events within the schedule for any user in the company. |
| **manage_no_schedule** | false | Not able to create/edit/delete events within the schedule for any user. |
| **view_company_schedules** | false | Able to view published events within the schedule for any user in the company. |
| **view_group_schedules** | false | Able to view published events within the schedule for the groups that the user is a member of. |
| **view_my_schedules** | false | Able to view published events within the schedule for themselves. |

 <aside class="notice">
The <code>submitted_to</code> and <code>approved_to</code> properties required the <i>approvals addon</i> to be installed.
</aside>

 <aside class="notice">
The <code>submitted_to</code> property is <i>read-only</i> unless the account setting <code>approvals->settings->employee_approval = 1</code>.  See <a href="#effective-settings">Effective Settings</a> documentation for details.
</aside>

 <aside class="notice">
When updating the <code>approved_to</code> date, if the value is greater than the <code>submitted_to</code> date for this user, both properties will be updated.  This is the equivalent of a manager/admin submitting time on a user's behalf.
</aside>

 <aside class="notice">
The following fields are considered <i>private</i> and are exposed only to managers and admins:
  <code>employee_number</code>, <code>salaried</code>, <code>exempt</code>, <code>username</code>, <code>payroll_id</code>, <code>hire_date</code>,
  <code>term_date</code>, <code>mobile_number</code>, <code>submitted_to</code>, <code>approved_to</code>, <code>permissions</code> & <code>customfields</code>
</aside>

 <aside class="warning">
 The following fields are <i><b>deprecated</b></i> for User Create and Update operations:
 <code>require_password_change</code> & <code>password</code>
 </aside>

