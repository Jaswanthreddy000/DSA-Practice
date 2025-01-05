## Theeyagura Jaswanth Reddy

## Submission checklist

- [x] Your submission follows best practices for [commit messages](https://chris.beams.io/posts/git-commit/) AND for [pull requests](https://github.community/t/best-practices-for-pull-requests/10195)
- [x] `Steps to run the project` AND a `documentation` have been included in a README.md file at root of your project.
- [x] No `binaries/compressed` files have been added
- [x] All pre-existing files in the repository have been removed
- [x] `Screenshots` have been added to the screenshots folder (optional for backend code).
- [x] All italicesed instructions under each submission heading inline, have been removed.
- [x] You understand that a submission here is publicly visible. 
- [x] You have not plagialised, or blatently copied work; and this submission is your original work. (Code of ethics)

## Briefly write about the project that you have submitted from the perspective of the user.
- This project is a Form Builder Application that allows an admin to create dynamic forms with multiple types of questions (text, checkbox,dropdown) and also view the analytics of the responses submitted by users.
- Users can fill out these forms, and the admin can view the responses and analyze data efficiently. 
- The Admin can add, edit, and delete forms or questions as required. 
-  For Each Form Admin can order the questions in any order.
-  For Each Question Admin can also order the options(checkbox,dropdown) for each quesiton.
-  Form can be submitted only if all the questions are answered.
(atleast one checkbox needs to selected for sucessful form submission)
- The platform ensures user-friendly management and tracking of responses.



## Assumptions you have made for this project?
- Admins can create forms and edit forms and also see the analytics of the form, responses of the form and also the answers of the form.
- End User can add multiple responses from the link given and select the form to give reply by clicking on add new response(or by sharing the link of the new response)and also view the analytics of the form.
- Understood to create a order for options and questions in each form such that they can sorted ascending or descending order
-Also in analytics page only if the contents are above 5 only then others will be displayed.


## Other information (like testing credentials)
- This project does not require any special credentials to run the application.
- The platform can be used with any admin account for testing purposes.
- No external APIs are used in this project.

## Did you learn anything new while doing this assignment? Please explain.
- Added a order field to questions and also a order field to options of each question in which way they must be displayed for the user.(This will be very helpful in case of assessment to randomize questions and options).
- Added a filter method in admin for questions to view by questiontype(text,dropdown,checkbox) and also a filter method for options to filter option by question.
- Also understood Django REST Framework (DRF) in detail and how to handle various scenarios.


## How much time did it take for you complete the project?
- It took me around 20 hours to complete the project from designing database models, views, creating user-friendly UI pages and then creating and also adding the admin panel for superuser.


## If you had more time, what enhancements will you make?
- Create a more user-friendly frontend for admin to dynamically create forms, edit forms, delete forms rather than using superuser
- Able to add timed forms which can be used for assessments.
- Able to implement a random order of question such that different users will receive questions in different order which is useful incase of assessments.
- Also in case of a assessment provide result for the exam matching with the users response with answers.
- Advanced analytics with  dynamic charts, graph analysis of user responses.
- Also add percentage completion of the form such that user can understand how much of the form is answered.

