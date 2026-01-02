# FixIt - Public Problem Reporting System

A full-stack web application that allows citizens to report public problems like broken streetlights, potholes, or garbage overflow. The system stores this data and displays it on an Admin Dashboard where authorities can review and manage the reports.

## 🌟 Features

### User Features
- **Report Issues**: Submit problems with photos, descriptions, and locations
- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Image Upload**: Support for uploading photos of reported issues
- **Location Detection**: Manual location input with optional auto-detection
- **Status Tracking**: View the current status of reported issues

### Admin Features
- **Dashboard**: View all reported issues in an organized card layout
- **Status Management**: Update issue statuses (Pending, In Progress, Resolved)
- **Statistics**: Overview of reports by status
- **Search & Filter**: Find specific reports quickly

### Technical Features
- **Modern UI**: Clean, professional design with Bootstrap-like styling
- **AJAX Integration**: Dynamic loading without page refresh
- **Form Validation**: Client-side and server-side validation
- **Error Handling**: Comprehensive error messages and logging
- **Security**: Input sanitization and SQL injection prevention

## 🛠️ Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Backend**: PHP 7.4+
- **Database**: MySQL 5.7+
- **Server**: Apache/Nginx (XAMPP/WAMP recommended for local development)

## 📁 Project Structure

```
/FixIt
├── index.html                    # Home Page
├── report.html                   # Report Issue Page
├── dashboard.html                # Admin Dashboard
├── assets/
│   ├── style.css               # Main stylesheet
│   ├── script.js               # JavaScript functionality
│   └── images/
│       └── placeholder.png     # Default image for reports
├── backend/
│   ├── db_connect.php          # Database connection
│   ├── submit_report.php       # Handle report submissions
│   ├── get_reports.php         # Fetch reports for dashboard
│   └── update_status.php       # Update report status
└── fixit_db.sql               # Database schema and sample data
```

## 🚀 Installation & Setup

### Prerequisites
- XAMPP/WAMP/MAMP installed and running
- PHP 7.4 or higher
- MySQL 5.7 or higher
- Web browser (Chrome, Firefox, Safari, Edge)

### Step 1: Download and Extract
1. Download the FixIt project files
2. Extract to your web server's document root (e.g., `C:\xampp\htdocs\FixIt`)

### Step 2: Database Setup
1. **Start MySQL** in your XAMPP/WAMP control panel
2. **Open phpMyAdmin** (http://localhost/phpmyadmin)
3. **Import the database**:
   - Click "Import" tab
   - Choose `fixit_db.sql` file
   - Click "Go" to import

### Step 3: Configure Database Connection
1. Open `backend/db_connect.php`
2. Update the database credentials if needed:
   ```php
   $host = 'localhost';
   $dbname = 'fixit_db';
   $username = 'root';    // Change if different
   $password = '';        // Change if you have a password
   ```

### Step 4: Set Permissions
1. **Create uploads directory**:
   ```
   Create: assets/images/uploads/
   ```
2. **Set write permissions** for the uploads folder:
   - Windows: Right-click folder → Properties → Security → Edit permissions
   - Linux/Mac: `chmod 755 assets/images/uploads/`

### Step 5: Test the Application
1. **Start Apache** in your XAMPP/WAMP control panel
2. **Open your browser** and navigate to: `http://localhost/FixIt/`
3. **Test the functionality**:
   - Submit a test report
   - Check the dashboard
   - Update report status

## 📋 Usage Instructions

### For Citizens (Reporting Issues)
1. **Navigate to the Report Page**:
   - Click "Report Issue" from the navigation menu
   - Or go directly to `http://localhost/FixIt/report.html`

2. **Fill the Report Form**:
   - **Upload an image** (optional but recommended)
   - **Describe the problem** in detail
   - **Provide location** information
   - **Submit the report**

3. **Confirmation**:
   - You'll see a success message
   - Your report is now in the system

### For Administrators (Managing Reports)
1. **Access the Dashboard**:
   - Click "Dashboard" from the navigation menu
   - Or go directly to `http://localhost/FixIt/dashboard.html`

2. **View All Reports**:
   - Reports are displayed in card format
   - Each card shows: image, description, location, status, date

3. **Update Status**:
   - Click on the status badge to change it
   - Choose from: Pending, In Progress, Resolved
   - Changes are saved automatically

4. **Monitor Statistics**:
   - View summary statistics at the bottom
   - Track pending, in-progress, and resolved issues

## 🔧 API Endpoints

### Submit Report
- **URL**: `/backend/submit_report.php`
- **Method**: POST (multipart/form-data)
- **Parameters**: description, location, image (file)
- **Response**: JSON with success status

### Get Reports
- **URL**: `/backend/get_reports.php`
- **Method**: GET
- **Response**: JSON array of all reports

### Update Status
- **URL**: `/backend/update_status.php`
- **Method**: POST (application/json)
- **Parameters**: report_id, status
- **Response**: JSON with update confirmation

## 🧪 Testing

### Manual Testing
1. **Home Page**: Verify navigation and content display
2. **Report Form**: Test form validation and submission
3. **Image Upload**: Test file upload with different formats
4. **Dashboard**: Verify report loading and status updates
5. **Responsive Design**: Test on different screen sizes

### API Testing
Use tools like Postman or curl to test the backend APIs:
```bash
# Test get_reports.php
curl http://localhost/FixIt/backend/get_reports.php

# Test update_status.php
curl -X POST http://localhost/FixIt/backend/update_status.php \
  -H "Content-Type: application/json" \
  -d '{"report_id": 1, "status": "In Progress"}'
```

## 🔒 Security Considerations

- **Input Validation**: All user inputs are sanitized
- **File Upload**: Restricted file types and sizes
- **SQL Injection**: Prepared statements used throughout
- **Error Handling**: User-friendly error messages
- **File Permissions**: Proper directory permissions set

## 🐛 Troubleshooting

### Common Issues

1. **Database Connection Failed**
   - Check MySQL is running
   - Verify credentials in `db_connect.php`
   - Ensure database is imported

2. **Image Upload Not Working**
   - Check uploads directory exists
   - Verify write permissions
   - Check PHP file upload limits

3. **Reports Not Loading**
   - Check browser console for errors
   - Verify API endpoints are accessible
   - Check PHP error logs

4. **Status Update Fails**
   - Ensure JavaScript is enabled
   - Check network tab for API responses
   - Verify database connection

### Getting Help
- Check the browser's developer console for error messages
- Review PHP error logs in your server logs
- Ensure all files are in the correct locations
- Verify database connection settings

## 🚀 Future Enhancements

### Planned Features
- **User Authentication**: Login system for citizens and admins
- **Email Notifications**: Automatic notifications for status changes
- **Google Maps Integration**: Interactive map for location selection
- **Search & Filter**: Advanced filtering options
- **Export Functionality**: Export reports to CSV/PDF
- **Mobile App**: Native mobile application
- **Multi-language Support**: Support for multiple languages

### Technical Improvements
- **Caching**: Implement caching for better performance
- **Rate Limiting**: Prevent spam submissions
- **Image Optimization**: Automatic image compression
- **Analytics Dashboard**: Detailed reporting and analytics
- **API Documentation**: Comprehensive API documentation

## 📞 Support

For questions, issues, or contributions, please contact:
- **Email**: support@fixit-system.com
- **GitHub**: [github.com/fixit-system](https://github.com/fixit-system)
- **Documentation**: [docs.fixit-system.com](https://docs.fixit-system.com)

## 📄 License

This project is open source and available under the MIT License.

## 👥 Credits

**Developed by:**
- Faraz Hussain
- Ali Raza

**Institution:** Sukkur IBA University

**Special Thanks:** To our professors and mentors who guided us through this project.

---

**Making communities better, one report at a time.** 🌟