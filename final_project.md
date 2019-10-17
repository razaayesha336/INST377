Through the group project in the INST 377 class, students are expected to design and build a web application that runs on a real server (VCL, AWS, etc). Particularly, technology, design AND management in the group project need to be justified well in your presentations and documentations, since communicating technology with both developers and non-technical people is a very important qualification in the real-world as well as in academia. Evaluation criteria and directions are presented below.

### Final Application Folder Structure
```
/docs
/src
-- /static
---- images, etc. for development
-- /css
-- /js
-- index.html
-- development files
/build
-- index.html
-- any built files
-- /css
-- /static
-- /js
---- images, files that don't change, etc.
.eslintrc.json
.gitignore
package.json
README.md
... etc.
```

## Final Reports
Each team is expected to submit:
1. User Manual (docs/user.md)
    * This document should be used to explain the application and its use to your identified stakeholders.
    * It explains how they should use the system.
    * It should be written in clear, plain, non-technical language.

2. README  (top part of your README.md)
    * Title of your project
    * Description of your project
    * Link to the Heroku, Netlify, or Digital Ocean instance where your application can be used
    * Description of target browsers (iOS? Android? Which ones?)
    * Link to User Manual 
    * Link to Developer Manual

3. Developer Manual (bottom half of your README.md)
    * The audience of this document is future developers who will take over your system.
    * They know technical terms and have general knowledge about web applications, but do not have knowledge about your system design.
    * You need to provide a technical document so that future developers can start setting up the application on their local machines, and keep working on the system development after you leave the team.
    * Your Developer Manual covers:
      * How to install your application and all dependencies
      * How to run your application on a server
      * How to run any tests you have written for your software
      * The API for your server application - all GET, POST, PATCH, etc endpoints, and what they each do
      * A clear set of expectations around known bugs and a road-map for future development.

4. Final Report (docs/final.md)
    This rest of the document is a brief description of your final presentation.
    * Title 
    * Team members
    * Link to where your app is running
    * Information problem you're trying to solve
    * Identified stakeholders/target browsers
    * Data you chose to work with
    * Chosen strategies and solutions for the problem
    * Technical system decision rationale
    * How/if your final system helps to address the problem
    * Challenges faced and impact on final design
    * Possible future work directions with this problem
      
* Documentation needs to be written in Markdown (MD) files, nicely formatted
* Documentation should be included to each team’s final code submission.
* Documentation should be saved in your main project directory under "docs"
* Docs should be submitted as either fully-styled HTML & CSS or a PDF file
 
### Minimum Code Guidelines
#### Front End - 40%
* Front end displays correctly in at least two devices from a single code base
* Front end accesses data fully through AJAX data loads
* Front end is styled using contemporary CSS, including appropriate use of flexbox or grids
* Front end styles appear similar on all contemporary desktop browsers
* Minimum 3 application pages:
  1. Index, where we can access your app
  2. About, describing the project
  3. Documentation for developers looking to work with the project

#### Back End - 40%
* Successful connection to external data source
* All application token secrets installed properly
* Installed on a SaaS portal - Heroku, Netlify, Digital Ocean, etc.
* 3 API end-points you have authored, which:
  * Get data from an outside source
  * Transform it to help solve your information problem
  * Pass it to the front end
* A GET endpoint, a POST endpoint, and a PUT endpoint
* End points can be accessed from and supply data to the front end
* **Extra credit**: Make your own local database that can store POST information
* **Extra credit**: Use GraphQL and Apollo to write a GraphQl access grammar

#### User Experience Design - 20%
* Application uses a contemporary color scheme in an effective way
  * Tool: [Kuler by Adobe](https://color.adobe.com/create)
* Application uses a coherent approach to font selection and sizing
* Application makes good use of responsive web design principals
* Application loads data at appropriate times to not block client experience
* Application loads appropriate amount of information/images/etc for platform
* Application works smoothly on 3 bars of service, no WiFi


### Extra Credit
There are several opportunities for extra credit on this project:
* Use React for your front-end, and design it to update dynamically
* Use advanced CSS animations for all your motion on the front end
  * Button clicks, swipes, screen transitions
* Use a design grammar such as Material or iOS to establish a coherent design voice
* Choose fonts and colors that compliment one another to make a strong user experience
* Application stores local data properly to be useful without wifi