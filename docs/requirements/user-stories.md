# User stories 

## Define 
- Project: a Project object represented by a post on personal website 
- Project list: a list of Project object 
- Project metadata: title, publication date, description, thumbnail, and tag 
- Tag: a categorization for projects 

## Visitor 
who view the content 
- As a visitor, I want to see the introduction and browse project list, so that I can read content without logging in
  ```
  Given a visitor
    And a website with published project 
  When the visitor navigates to the project page 
  Then the visitor sees a list of project with project metadata with a tag list 
    And the visitor can scroll through the list 
    And the visitor can click on a project to view full content
  ```
- As a visitor, I want to view a specific project, so that I can read its full content
  ```
  Given a visitor
    And a website with published project  
  When the visitor clicked on a project in the list  
  Then the visitor sees full content of the project
    And the visitor sees the project's metadata
    And the visitor can scroll through the content 
  ```
- As a visitor, I want to search for articles / filter by tag, so that I can find content relevant to my interest 
  ```
  Given a visitor 
    And a project page with search bar  
  When the visitor enters a keyword in the search bar
  Then the system displays a list of projects matching the keyword updated in real-time
    And each include the project metadata 
    And the visitor can click on a project to view its full content
  ```
  ```
  Given a visitor 
    And a project page with tag lists  
  When the visitor can select a tag from the tag list 
  Then the system displays a list of project containing the tag
    And each project include the project metadata 
    And the visitor can click on a project to view its full content
  ```
- As a visitor, I want to see a related project section, so that I can discover more articles related to my interest 
  ```
  Given a visitor, 
    And a project detail page 
  When the visitor scroll to the bottom of the page 
  Then the visitor sees a list of related project 
    And the visitor can click on a project to jump to that project detail page 
  ```
- As a visitor, I want to subscribe to a newsletter, so that I receive updates on new content
  ```
  Given a visitor 
    And a website with a newsletter subscription option 
  When the visitor enter their email address in the subscription field 
    And click "Subscribe" button 
  Then the system sends a email to the visitor
  And the visitor sees a message confirming that a verification email has been sent 
  ```
  ```
  Given a user 
    And a valid confirmation email in their inbox
  When the visitor clicks the verification link in the email 
  Then the system confirms the subscription 
    And the visitor is added to the newsletter mailing list
    And the visitor receives a welcome email 
  ```

## Owner
who manage the content and view the web traffic data 
- As the owner, I want to log into my account, so that I can manage sensitive information 
  ```
  Given the owner
    And a website with an authentication system 
  When the owner navigates to the login page 
    And enters their valid credentials 
    And clicks the login button 
  Then the system verifies the credentials 
    And grants the owner access to the admin dashboard 
  ```
- As the owner, I want to log out, so that I can secure my account when I'm done working 
  ```
  Given the owner
    And an active session in the admin dashboard  
  When the owner clicks the "logout" button 
  The the system terminated the session 
    And redirects the owner to the login page 
  ```
- As the owner, I want to reset my password, so that I can regain access if I forget my credentials 
- As the owner, I want to connect my login to external accounts like Google, GitHub, etc, so that I can easily login without entering password 
- As the owner, I want to create a project, so that I can showcase my work on my personal website 
  ```
  Given the owner 
    And a desktop/mobile application 
  When the owner clicks the "create project" page 
    And enter the metadata (optional except title) 
    And clicks the publish button 
  Then the system saves the project as a new project 
    And the project appears in the project list on the website 
    And the owner sees a confimation message 
  ```
- As the owner, I want to edit an existing project, so that I can update its content and metadata 
  ```
  Given the owner 
    And an existing project on the website 
  When the owner navigates to the project page in the application 
    And updates metadata or content 
    And clicks the "publish" button 
  Then the system updates the project on website 
    And the owner sees a confimation message 
  ```
- As the owner, I want to delete a project, so that I can remove unwanted content 
  ```
  Given the owner 
    And an existing project on the website 
  When the owner navigates to the project page in the application 
    And click "delete project" button  
  Then the system delete the project on website 
    And the owner sees a confimation message 
  ```
- As the owner, I want to add, edit, and remove tags from projects, so that I can categorize them properly 
- As the owner, I want to publish or unpublish a project, so that I can control its visibility on my website
  ```
  Given the owner
    And an existing project in the application
  When the owner toggles the project’s "Published" status
  Then the system updates the project's visibility on the website
    And the project either appears or disappears from the public project list
    And the owner sees a confirmation message
  ``` 
- As the owner, I want to view the website traffic data, so that I can understand how many people visit my site, how people engaged with individual projects 
  ```
  Given the owner
    And a website with an analytics dashboard
  When the owner navigates to the admin dashboard page
  Then the system displays a summary of visitor traffic data
    And the owner can see total visitors, page views, and session durations
  ```