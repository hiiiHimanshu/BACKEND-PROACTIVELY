# Demo Guide: Using the Admin Account

This guide walks you through using the admin account to create and manage collaborative forms with different field types.

## Getting Started

### 1. Login as Admin
- Navigate to `http://localhost:3001`
- Use these credentials:
  - **Email**: `admin@example.com`
  - **Name**: `Admin User`
- Click "Login"

### 2. Explore Pre-created Forms
The system comes with 4 sample forms demonstrating different use cases:

#### Team Survey (Share Code: TEAM2024)
- **Text Field**: Team Name
- **Number Field**: Project Rating (1-10)
- **Dropdown**: Department selection
- **Textarea**: Additional Feedback

#### Event Registration (Share Code: EVENT24)
- **Text Fields**: Full Name, Email Address
- **Number Field**: Number of Attendees (1-5)
- **Dropdowns**: Meal Preference, T-Shirt Size
- **Textarea**: Special Requirements

#### Product Feedback (Share Code: PRODUCT)
- **Text Fields**: Product Name, Favorite Feature
- **Number Fields**: Overall Rating (1-5), Likelihood to Recommend (0-10)
- **Dropdown**: Usage Frequency
- **Textarea**: Improvement Suggestions

#### Employee Onboarding (Share Code: ONBOARD)
- **Text Fields**: Employee ID, Full Name, Position, Emergency Contact details
- **Number Field**: Years of Experience (0-50)
- **Dropdowns**: Department, Work Location Preference
- **Textarea**: Additional Notes

## Creating New Forms

### Step 1: Access Create Form Tab
- Click on the "Create Form" tab in the main interface
- This tab is only visible to admin users

### Step 2: Fill Form Details
- **Form Title**: Enter a descriptive title (e.g., "Customer Satisfaction Survey")
- **Description**: Add context about the form's purpose

### Step 3: Add Form Fields
The system supports 4 field types:

#### Text Fields
- **Use for**: Names, emails, short responses
- **Example**: "Customer Name", "Company", "Email Address"
- Check "Required" if the field must be filled

#### Number Fields
- **Use for**: Ratings, quantities, ages
- **Example**: "Age", "Rating (1-10)", "Number of employees"
- Automatically validates numeric input

#### Dropdown Fields
- **Use for**: Multiple choice selections
- **Example**: "Department", "Country", "Satisfaction Level"
- Options are defined when creating the field
- **Note**: Currently options are set in the database, but you can modify the interface to allow dynamic option entry

#### Textarea Fields
- **Use for**: Long-form responses, comments, descriptions
- **Example**: "Feedback", "Comments", "Detailed Description"
- Provides multi-line input area

### Step 4: Configure Field Options
- **Field Name**: Clear, descriptive label
- **Field Type**: Select from dropdown
- **Required**: Check if field must be completed
- **Add/Remove**: Use buttons to manage multiple fields

### Step 5: Create and Share
- Click "Create Form" to generate the form
- System automatically generates a unique share code
- Share the code with participants

## Testing Collaborative Features

### Multi-User Testing
1. **Open Multiple Browser Windows/Tabs**
   - Window 1: Login as admin (`admin@example.com`)
   - Window 2: Login as user (`user1@example.com`)
   - Window 3: Login as user (`user2@example.com`)

2. **Join the Same Form**
   - Use share codes: TEAM2024, EVENT24, PRODUCT, or ONBOARD
   - All users join the same form

3. **Test Real-time Features**
   - **Field Locking**: Click on a field in one window, see it lock in others
   - **Live Updates**: Type in one window, see changes in real-time in others
   - **Participant Tracking**: See active users listed at the top
   - **Visual Indicators**: Locked fields show who's editing

### Field Type Demonstrations

#### Text Field Testing
- **Single Line Input**: Test with names, emails
- **Real-time Sync**: Type and see updates across browsers
- **Field Locking**: Focus locks field for other users

#### Number Field Testing
- **Validation**: Try entering non-numeric values
- **Min/Max Ranges**: Test boundary values
- **Real-time Updates**: Number changes sync instantly

#### Dropdown Testing
- **Option Selection**: Choose different options
- **Sync Behavior**: Selection updates across all users
- **Locking**: Dropdown locks when one user is selecting

#### Textarea Testing
- **Multi-line Input**: Test longer text entries
- **Real-time Typing**: See character-by-character updates
- **Scroll Sync**: Large text areas maintain position

## Advanced Testing Scenarios

### Conflict Resolution
1. **Simultaneous Editing**
   - Two users try to edit the same field
   - First user gets the lock, second sees "locked" indicator

2. **Connection Loss**
   - Close one browser tab
   - Field locks automatically release
   - Other users can immediately edit

3. **Rapid Switching**
   - Quickly move between fields
   - Locks acquire and release smoothly

### Performance Testing
1. **Multiple Participants**
   - Add 3-5 users to the same form
   - Test responsiveness with multiple active editors

2. **Large Forms**
   - Create forms with 10+ fields
   - Test scrolling and field navigation

3. **Long Sessions**
   - Keep forms open for extended periods
   - Verify memory usage and connection stability

## Sample Form Ideas to Create

### 1. Customer Feedback Form
\`\`\`
Title: Customer Satisfaction Survey
Fields:
- Customer Name (text, required)
- Email (text, required)
- Service Rating (number 1-5, required)
- Service Type (dropdown: Support, Sales, Technical, required)
- Comments (textarea, optional)
\`\`\`

### 2. Project Planning Form
\`\`\`
Title: Project Requirements Gathering
Fields:
- Project Name (text, required)
- Budget Range (number, required)
- Timeline (dropdown: 1-3 months, 3-6 months, 6+ months, required)
- Team Size (number, required)
- Requirements (textarea, required)
\`\`\`

### 3. Event Feedback Form
\`\`\`
Title: Workshop Evaluation
Fields:
- Participant Name (text, required)
- Session Rating (number 1-10, required)
- Most Valuable Topic (text, optional)
- Improvement Areas (textarea, optional)
- Recommend to Others (dropdown: Yes, No, Maybe, required)
\`\`\`

## Troubleshooting

### Common Issues
1. **Form Not Loading**: Check database connection and form permissions
2. **Real-time Not Working**: Verify WebSocket connection in browser dev tools
3. **Field Locks Stuck**: Refresh browser to clear stale locks
4. **Participants Not Showing**: Check network connectivity and authentication

### Browser Developer Tools
- **Network Tab**: Monitor WebSocket connections
- **Console**: Check for JavaScript errors
- **Application Tab**: Verify localStorage tokens

## Next Steps
- Test with real users in your organization
- Customize field types for specific needs
- Deploy to production environment
- Add additional features like form templates or analytics
\`\`\`

Now let me also create a quick reference card for the admin interface:
