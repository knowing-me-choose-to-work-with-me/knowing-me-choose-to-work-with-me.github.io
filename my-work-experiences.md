## My Work Experiences
- [Work-Experiences](#work-experiences) 
    - [Company-4-GE Oct-2018 to Jan-2024](#company-4-ge-oct-2018-jan-2024)
        - 5.3 years - discovering myself as software-engineer, system-designer, data-modeler, architect
    - [Company-3 Wipro Apr-2016 to Jul-2018](#company-3-wipro-apr-2016-jul-2018)
    - [Company-2-CSC Dec-2009 to Mar-2016](#company-2-csc-dec-2009-to-mar-2016)
        - intro to consultancy, deputation, 
    - [Company-1-Tomax Jun-2005 to Sep-2009](#company-1-tomax-jun-2005-to-sep-2009)
        - [Retail](#retail) 4.3 years | inventory-mgmt | demand-forecasting | 
        - intro to corporate culture, foundations for  software development as taught by my-great-mentor who taught not execute until the output is conceived in mind.
- [Home](#site-map)

   
## Work-Experiences
 
## Company-4-GE Oct-2018 Jan-2024
-  5.3 years - discovering myself as software-engineer, system-designer, application-architect, solution-architect 
### aviation-domain-exposure 
- the-Engine-product , after-market-service-agreement, the-margin-review
- [ge-aerospace](https://www.geaerospace.com/sitemap) [GE-wiki](https://en.wikipedia.org/wiki/GE_Aerospace) my exposure is on in-house software tools and applicaitons built for [commercial-services](https://www.geaerospace.com/commercial/services)
- the way, I have understood, on the space i got exposed to, and everything what I worked for in GE  starts with an engine coming to shop-visit, then many appliations digitize  on the MRO (overhaul repair,replacement of parts etc). The services offered are very customized for each customer be it airline or airframer which they call by customized-service-agreements CSAs which span from 5 to 20+ years of contract, GE has x-margin-profit which are reviewed CMRs(contractual-margin-review) annually on a pre-defined quarter. The basic idea is to check the MRO cost incurred for the set of engine which came to shop. So, every quarter of the year, they check or review(to-be-precise) on the x-margin-tobe-realized which was signed with customer to see if its profitable or not. if not then to make some adjustments on cost trading off repair vs replacement-of-parts((old,new)) or send them to another MRO shops spreaded across the globe where the labor cost is cheaper. For some Engines like CFM56, Leap due to JV say 50:50 the revenue gets shared. The complexity continues like this on how ge charges/bills customer on several factors like temperature, altitude, thrust and utilization(just like my-bike-service)
    - GE Purpose "We invent the future of flight, lift people up and bring them home safely"
    - culture-perse : in-my-view though I could be wrong, I imagine it to be pyramid of  people(bottom), process, techonology(top) and due to the very nature of business they usually put safety and security at top. so even for inhouse-software solutions which are not internet  facing still to use a technology, process and multi-level approvals are always deeply inherent in the culture. I should admit that there are lot of good problems(modeling-analytics-simulation) to be exploited and  solved. I also felt that I was evolving as a good software engineer during my tenure for the support I got from my immediate-managment and colleagues support. 
    - since childhood, I have great interest in aeroplanes, its fascinating to watch them fly, although i kind of dont like long-journey in plane due to conjusted seating, I usually  prefer aisle seat, so that I can strech my legs.
        - Personally, I had put a lot of effort, extr-hours in understanding the engine its parts, modules etc CMRs, CSAs, upstreams, downstreams   scanning through confluences, recordings and countless conversations with my ge-colleagues, vendor-partners. This had helped me to stretch for almost 5+ years in GE solving different problems. The culture is pretty good for learning if you like the domain.
- some key memorable things in my entire tenure of GE
    - [GIDS conference](https://developersummit.com/) sponsored by GE
        - sessions from neal-ford, mark richards, scott davis and few other changed changed my approach on microservices design, architecture, domain-driven-design, front-end tricks etc
        - i applied several techniques from these , discarded some concepts of 12-factor heroku approach.
        - some techniques like jdbc over hibernate, domain-driven-design  were not new to me, however hearing from expert boosted my confidence  in that direction. I was able to build stuff with confidence, talked/advocated to my team on tradeoffs etc
        - Now, I make a good attempt to attend every year
    - 2.5 days jets lite where you get a great opportunityto dismantle a small engine, with lot of safety gear and team-work-stuff

- ### project-1 (workflow-orchestrator)
- Clearview CMR
- my intro to microsevices-with-spring-boot, aws-cloud, cicd-pipeline, aviation-domain
    - having a strong grip on servlet, soap-webservices,  I discovered, these are now replaced with @restcontroller @service, @entity. 
    - lot of data-access like jdbc DAO, DTO was simplified with higher abstractions offered by JPA @respository and @JDBCTemplate
    - Thanks to cloud, now I had visiblty to machines hosted where the (service,datbase,frontend-app) ran
    - This visiblity to cloud gave clear cut idea that we can now leverage cpu GHz, ram-memory 4 to 8gb , started making several attempts to leverage on these concepts for every functionas-requriements
- my role   
    - Initially, played a backend-developer, then evolved to more of technical-lead taking care of entire design and architecture.
- Purpose of overall Tool - In-house tool 
    - The original authors and to certain extent my vision of it to be a
        - automation tool to collborate on cmr documents, modeling inputs, outputs  across models(technical,financial)
        - a cmr-workfloworchestrator automating 80+ cmr steps/tasks 
        - a cmr kickoff tool, signoff tool, workflow-progres tool, an integration-tool
        - Served high-level personas for CMRs
   
-  My design decisions, tasks, contributions 
    - my initial work started with testing, feasiblity of flowing all-cmrs-data to a downstream in one-shot, a performance-issue which was addressed by tweaking sql (removing few co related queries and nested joins and moving a piece of it for service-layer)
        - the peformance-issue and some attention
            - There was a requirement to capture all the activities, user did on the overall workflow, it  was captured on a events table with delta-change of step/task, only top 20 or 30 activiteis were useful and shown on the screen, yet the service pulled all the events table which kept on growing day by day connected with some important tables, and each time some one went to activities screen, occassionaly it was 10 to 20k records,  it took 7 to 8 mins to load for couple of scenarios, occassionaly that particular microservice failed, crashed . Team just restarted the microservice manually by running a chef script. after careful observations, I made a  disovery that though there were 10 to 20k of records, at back of sql it did join several 100k recores, I did  apply a fix by removing nested query joins and co-related queries and even moved fetching a set of records and its aggregation logic to service layer from database logic. Now it just took few seconds (i guess < 10 seconds). Now, I got some attention from my backend developers team.
    - automation-1-FleetFlex-Integration : 
        - started as a developer, collaborator with other architects, and eventually led the whole design and implemenation, and then guided team for subsequent changes
        -  so far this application had only 1 integration with downstream for financial-modeling-space,  the 2nd integration came  for another  downstream for technical-modeling-space on which requirement kept changing for next 6 months or so.
        I made few things very clear,  to keep design simple, stupid, extensible and flexible. Because the discussion suggested lot of unknowns, some future changes, also political-conflicts for uknown-reasons to me.
        Being cmr-workflow-data-prouducer and an upstream orchestrator. I did 2 things further to help me for quick changes
        1. Devised api contract codes for each of the business use case. Froze on contract codes but gave option for extensibity by adding new codes
        2. Rather, tightly coupling and designing for java objects , i choose to parse the json payload, got some dirty pollution of json code, but it was quick to make any change for  downstream application request.
            - Before I left the project, i converted back to java objects for others readability.
        Both helped me to have a good control and I could litterally make changes as soon as I heard change in requirement and do a git push, for qa testing.
    
    - automation-2-OpsParam-KPI 
        - Guided team on design and data-model for this requirement.
        - Purpose:  to capture some 36 months for severity factors of engine-flew like flight-leg, utilization, derate,temperature
        Two of  my young colleagues had a good grip on business-domain and also had a good depth on implementation as well, so  I just guided them on design and advocated on JDBC batch processing with an diffrent approach to store 2d array. 
        With good brainstorming,  we projected the data volume growth for 10 plus years, this helped in giving clear directions to stakeholders including to retain the history of summary backed by a history table to keep the actual summary to be rolling and relevant for current year.
        
    - automation-3-postprocessing-tagging   
        - my-role collaboration on  design with other architects and 
        -  a minor enhancement to tag on modeling-documents with  various postprocessing tools/applications, their outputs were to be shared by s3 bucket. This was my intro fascinating aws-s3 which has become an excellent storage tool for me.
    - automation-4-Finlization-step
        - my-role: design,implementation end to end, collaboration-with-stakholders
        -  finalizing a workflow step for a technical-modeling space one more to add on, it was just backed up an sql, however the business-discussions got heavy and stopped after working piece of delivered.
    - automation-5-CMR-signoff
        - my-role: collaboration-with-stakholders, desing, implementation and integration
        - purpose: to have a governance to approve a set of users to to agree if overall business for the given contract can be finalized to close the CMR for the financial year
        -  I took this for its criticallity, same old deviced contract codes, etc however took a math apporach to store plain numbers for the domain terms (lock(100),unlock(-100)signoff(200),re-approval(-200)), just a tiny math, but helped for reconciliation and backward compatiblity, aggragation in later. 
    - automation-6-interim-workflow-setup
        - my-role: guidance, collaboration with stakeholders
        - a small-feature (probably idea of 1 or 2 users) to introduce a interim iteration/workflow-setup, almost 8 weeks of effort
        - post-deployment to production, due to a change of mgmt, we were asked to take it out. we just applied a hack to turn off the feature.
    - automation-7-secure-file-upload
        - my-role: guidance on design
        -  To securely upload files, apply few defense-of-depth strategies like file extension, exploding archive and verifying contents etc.
    - automation-8-template-standardization
        - my-role: lead the design, data-model, collaboration-with-stakeholders(lot of burndown, conflict-mgmt, covid-chaos)
        - purpose : To standardize the cmr-workflow-setup, so that any upstream/downstream could mutually agree on what a task/step defintion meant, across various modeling-spaces
        - 
    - automation-9-Workflow-Hierarchy
        - my-role : collaboration-with-stakeholders,  played an IC, end to end design, implementation, data-model in mid of covid-chaos
            - built on top of a POC from my colleague-architect's serverless-integration with aws-lambda
        - purpose : to share the workflow-setup to down stream to a new replacement tool(SIM-SimulationInputManager) of automation-1-fleetflex-integration
        - a-little-story to share : 
            - First, I got a chance to work  along with my colleague-architect who interviewed me.He had couple of integration strategies sync,async. Knowing the application enough, I strongly insisted the synchronous communication (web-api) with KISS principle. we also brainstormed on technology to pick, I was more inclined toward exiting Java/springboot stack.My colleague-architect had visioned serverless in mind. No matter how we implemented it, it was bothering me that downstream application need to get/pull information needed from our-upstream-application with-in 2 to 5 seconds, because downstream had no clue on overall workflow and it can only get from us as upstream. They had a heavy dependency to select the contract, followed by the technical-modeling-workflow setup against the cmr, backed by a standardized-workflow-template devised by us-the-upstream. Only when they had these two flows could they kickstart theirs. So from serverless point of view, little google on aws-lambda warned on cold-start, so java was out of context(graal vm was in news, but wasnt tested), Finally as demonstrated by my other architect  with node.js/typescript, we noticed the server to be booted in a second or couple. This gave us a good confidence that if we could serve the data-pull in millis, then we could meet the SLA of 2 to 5 seconds. I built the most complex api query and verified that it took in 700 to 800 milllis. We zeroed on node.js/typscipt/aws-lambda. I sucessfully built all remaining apis and overall developemnt in 8 t 9 weeks.  My colleague-3-architect contributed on almost all cloud-formation templates, for aws-lambda. This helped me to focus on solving the overall business problem in a better way. production went smooth, in fact we deployed 1 day prior itself. It was a good learning for me, as well. We presented the the solution to larger audience, also noticed that serverless with integration was something we tried newly in much wider space of the org.on a side note, to keep the integration extensible and flexible I had leveraged sql views, complex joins and leveraged all buisness logic in it and  the typyescript service layer just handled the error scenarios and was dumb enough on any busincess logic.On a side note to verify system scalablity, we did a load testing with Jmeter simulating 500+ cmr domain events per second as opposed to ideal 30+cmrs per second. ofcourse it wasn't necessary looking at aws-lambda-concurrency of 1000s, however proof was needed to ensure confidence in all stakeholders.  
- some intersting observations to debate or discuss or improvise
    - Team org and evolution : 3 PO change, 2 Pod-lead, team size for 17+ to 6+
        - I myself rejected Pod lead role, for architectural-stuff
    - spreaded across 8 to 9 microsercies,  only 3 meant solving domain problem, rest 5 felt more of libary, shared service candidates
    - storage-db -  the data growth of appliation was hardly 32 MB by the time and by the time, i left it might have touched 100mb or so.  for an orchestrator for 3 to 5 years this was the data growth, I observed. The modeling inputs and outputs were stored on aws-EFS 
    - The key business-domain-event could have been roughly 30cmrs * 50steps spreaded across across each quarter , so this wasnt any data-centic application and I ocassionaly debated with my colleagues on hype/buzz against this. Probably I knew, too much on this data-model.

- ### project-2 the modeling problem
- Cost Model 
- Initial Reasons to bring me into this project
    - To my upper managment, it was request to get me a complex problem, with large-datasets
    - colleague-3-architect had visioned to solve some key performance, stuff called productivity projects
    - This was 90% vendor-partner heavy-team, so I was also tasked to see what we can solve differently
- my role
    - lead the technical design and architecture
    - a failed attempt to convert shared db acess to a wrapper service
- Purpose of overall Tool - In-house tool for cost-modeling-space
    - post digitization of shop-visits to MRO-shops, this as the first place were analysts could re-adjust the cost with either repair,replacement(new,used) and re-model them to differenet shops as well, so that they could re-adjust to what made sense for cost-optimization
    - It had pretty good models already built on regresssion for matured product lines
    - automation-1 There was an ongoing new thread to introduce Cost by ModuleByWorkscope
        - this modeling was applicable for current new product-lines GENX, Ge9x, LEAP and future ones
        - design-option-1   
            - there was 20 to 30% dynamic data which varied among 3 new-product-lines
            - The team had already gone to far in several business-flows, they had also applied  or was inherent with original design [EAV-data-model](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model) 

    - automation-2 This was supposed to be integrated with a downstream consumer(SIM) for which I had recently done the integration
        - design-option-1: 
            - the old fleetflex-tool had direct access to this shared-database, called the views exposed, The new replacement so called next-gen SIM-tool also had finalized to goforward with direct-access. 
    - some-eventual-discoveries
        - technically, this was purely a shared-database-architecture with on-prem-oracle
-  My design decisions, tasks, contributions 
    - automation-2 :
        - we saw the future problems, if direct access continued in future as well, for below concern
            - first, this was time-to-market, deliver asap, with least change, direct access to views meant tight locking of integration to database views , which interm suggested that this cost-model application cannot make any change to database, refactoring which could affect the running views.
            - second, there was no thought process to make sure to efficiently allow downstream application to consume in 100 of thousand records if it grew so.
            - third, based on how downstream made db connection to views, a connection failure could have halted its operation.
        - we proposed a new design to give a wrapper-service, to which they could have consumed, potentailly this would have addressed many above and on top of that myself and another data-architect had imainged to change the current architecture to nosql one. This didnt materialize probably we were late in the game.
    - automation-1
        - Purpose: with plenty of discussion with BA and our SME(vendor-partners) who had gained enough knowledge on domain, it appeared that for new product-lines it was difficult to model cost because the shop-visit could happen in future 3 to 5 years. Some analysts and stakeholder had cleverly devised a model to take engine parts with highest cost all the way module level and remodel to different shops, engine-models etc they had devised a formula having multiplied by a x % exposure-rate.
        - the current design-option-1 had few major conerns
            - first, even though analysts picked high part cost, we had to model for all the parts of engine, which they had filtered in a prevous buisness flow and then build all permuations(team-called-placeholder) for shops, regions, series, model etc. so no body was thinking through scale
            - second, a leap engine was by far the biggest one in volume, its volume/scale wasn't factored again
            - third, there were four modling-inputs , one part-level was already failing or crashing occasionaly
        - After, some heavy brainstorming, the third concern was re-emphasized to me, we projected the data-volume-growth and stared exploring some novel solutions to eliminate EAV-data-model which was the root cause, due to pivoting nature, the 100MB input was becoming more than a gig and SQL joins which connected to EAV-data-model-tables behaved misearbly slow. From 10 to 20mins 
        - My another colleague had  1 novel idea to leverage on AWS-glue baked by AWS s3 to eliminate the EAV-data-model with python as a service layer and parquet as format. Though it all sounded good. We kept this an open option design-option-2, I started exploring java-service with aws-s3 as design-option-3. 
        - design-option-3
            - I took  only the core piece of taking the 4 modeling inputs and rollup the cost and demostrated with no-sql option having done in few seconds for the worst one LEAP product-line
                - my rational choice for java, inspite of having python was simple and stupid. 95% of the team knew java-ecosystem, so had a future thought that if we cracked in java, it will open up doors for many other beyond this team as well
            - for visiblity and simplicity I simply preferred CSV over parquet.
            - also leveraged aws-s3-select so that other can think interms of sql
                - direct parsing with opencsv should have also been fine
            - partition on s3 prefixes with all the domain-attributes like product-line , analysis year
            - the aggregation, rollup all was done in java-service layer with mutations for full-performance benefit
            - the 20% dynamic data was handle with custom data-structure based on a dynamic array.
            - occasionaly, I had solved few beanstalk build and deployement issues.
            - pkg-by-feature structuring was also heavily leveraged
- outcome/result
    - the team was happy with EAV-data-model removed
    - during QA testing Leap rollup happened as fast as < 10 seonds
- some intersting observations to debate or discuss or improvise
    - for some reason for my entire tenure, from team I repeatedly heard the modeling inputs and outputs as reports, in reality they werent
    - There was plenty of scope for applying the regression-model it was limited to pull only 3 year data, with nosql we could have gone for even 10+ and beyond as well
    - There was plenty of good stuff  on visiblity the team had baked for the entire anaysis-flow, choosing all possible analysis of models was bit cumbersome and could have improvised.
    - 

- ### project-3 billing, reconciliation 
- Clearview Billing 
- Initial Reasons to bring me in
    - to stabilize the overall application
    - take a fresh look on the current design and architecture
- my role
    - recon-feature : lead the full end to end design and implemenation to productionizing it 
    
- Purpose of overall Tool - In-house tool for Billing
    - every month GE billed its customer based on an agreement with something called severity condition in which the engine flew as as opposed orginal agreed severity, Since the contracts were long term ranging from  to 20+ year, biller could charge an explicit dollar escalation.
    There was a new requirement with heavy push from top to incorporate an automation of reconciliation of older invoices. Billers (the-end-users) of app so far did this manually probably with lot of excel work
    - Design-Option-1 
        - to just add an reconciliation indicator, in all of the regular billing tables(database), service-layer, UI-layer 
        - With a time-to-market idea the team had already finalized this with buisness  as well 
    - some-discoveries to problems as couple months passed by with lot discussions
        - This system already had two components
            - cvb-1.0 the orignial old application  which had several limitations on billing-flexibility and on pretty much shared database architecture and heavy store-proc centric.
            - cvb-2.0 a brand new applicatin with modern tech-stack(java,springboot,vuejs, aws(ECS)) all invoicing 
            - there was a migration activity from app-1.0 to app-2.0 as well
            - this project had already gone with  several iterations, app-2.0 tool promised to be a next-gen tool, heavily betted on aws infra.
            - This was embedded in customer portal, so it also had different contols be it security, infra etc
            - wostcase-scale : some regural-monthly-billing(southwest-airline) took close to 10 mins and was worstening
            - There were also lot of tickets from billers on cvb2.0 automation to be stabilized
            - Team also struggled with single-master branch strategy and they usually worked on lot of tickets, features, bugs etc
            - Team, also had  a challenge in understaning the new ECS, codebuild aws-infra as I recall.
            - impact of $400 million every month 
-  My design decisions, tasks, contributions :
    - Reconciliatio-feature : lead the full end to end design and implemenation to productionizing it 
    - As, I reviewed and made several attempts to  fit the Design-Option-1 and ran in my mental models. Few things were bothering, 
        - First-concern,  it was more from a time-to-develop and deliver asap and concern-1 it didnt factor or devised any solution for  wostcase-scale. now from monthly-regular-billing to yearly there was 12x if you can imagine
        - second-concern, there was a 80% dynamic-schema play per invoice/bill based on severity factor the engine flew. There nothing done any thing to tackle it better,  The [EAV-data-model](https://en.wikipedia.org/wiki/Entity%E2%80%93attribute%E2%80%93value_model) was used to tackle it. Though at surface of iceberg it looked 4 factor of (temperature, utilization, altitutue, thrust) there were several derived attributes which could vary further based on Join Venture, Engine, customer to name few, they all were backed up by heavy formula as well.
        - third-conern, due to this reconciliation feature, there was high possibility of impact regular-invoicing to current runtimes of service and storage, my fear was service-crash and major performance to year-on-year. Which team wasnt noticing or thought of
    - I proposed two more desing options to tackle above concern
        - design-option-2 : to have multivalued array structure, in  the exisiting schema. json to eliminate the EAV-data-model backed by a new feature-service to isolate regular-monthly-billing. the rational choice was speed but reduce the pivoting of data-growth 
        - design-option-3 : leverage nosql storage for all three concerns backed by a new feature service.
    - contribution :
        - desinged and implemented design-option-3  end-to-end with help of a developer, QA(had a strong grip on the entire usecase, lot of credit goes for his clarity and simplfication).
            - On a sidenote like pandora-box the number of busines-flows went beynond 8, I had a good amount of burndown, Ideally I was suppose to work only of flow-4,flow-5 and flow-6 which did all core calculations, but end to end need to be seriously thought.
        - like my previous project , i landed with aws-s3 leveraged its prefix for data-partioning and address pretty much all 3 conerns
            - several-techniques like 1 network-call, in-memory-processing, mutataion of aggregations were heavily used.
        - this was further built with pkg-by-feature, embedded inside, regular invoicing.
        - the entire invoice-calculation-engine was reimagined and rebuilt.
        - validation-problem, The billers usually had to validate for lot of engines in some cases close to 600 to 1000, so devised a one shot validation cum possible fail scenario. so had built a new validation-engine to show new capability or help the biller in 1 go.  
        - adding new buisiness capablitiies like on file upload, i injected lot of pre-processing techniques (compuations,aggregations) upfront before user could click next-invoice-calculations. when user went for next step he got already computed results so it was just a dowloading a copy of computed results. The general idea was to add the whole computations on file upload itself. of course it comes with a adative code developement cost.
        - lot of low-level critical pieces like interpolation-engine was rebuilt and refactored from cvb 2.0
        - to help accelerate front end development, several 2d api were built at service and given to UI so that they could just blindly draw the matrix, saving serveral hours of development time.
        - refactored git-branching feature strategy
        - Helped team on making several other decisions as they surfaced in my tenure like git-branching-by-feature, some minor correction on aws-codebuild, ECS etc
    - people-who-helped-me in few hard-times 
        - QA without his clarity, the domain, some critical biz calculations could have been really hard to digest
        - colleague-3-architect on understading this portal-infra space and occasional build issues.
        - my manager and director to have covered on few timeline slippages and having patience on end solution
        - few developers(UI,service) who helped in flow1,flow-2,flow3
- outcome/result
    - the worstcase for regular-monthly-invoicing which took 10+ mintues for 600+ engines was now tested for 12x yearly reconcilation for 1000+ enignes invoicing time took was less than 10 seconds leveraging existing service-compute.
    - the buisness was promised on not to worry on data load for alteast 10+ years 
   
- ### project-4 data-strategy attempt in 2+ months
- data-strategy for cost-space
- Initial Reasons to bring me in
    - to take a fresh look what we can strategize in terms of data architecture for this most complex, upsteam cost-modeling suite of applications which had stored-proc heavy business-logic and share-database-architecture. 
- my role
    - To come up with a strategy 
- Purpose of cost-space
    - it was the most upstream suite of modeling-space an analyst would start with as eninge came to shop and digitized the MRO stuff
        - technically it was all shared-database(on-prem), full of stored-procs, each-app with its own copy of truth.
-  My recommendations, approaches, contribution
    - data architecture for entire cost space was overwhelming atleast to me, for below
        - first, its deep enough business logic hard-wired in storedprocs, hardly there were any experts left to decode it.
        - second, nobody wanted to touch/disturb this shared datbase architecture, if they did also lot of pushback from top-management
        - third, there was no master-static data to even orchestrate the product-wise or customer-wise data
    -  bit of reasearch took me in few directions
        - 1. to something called defensive strategy which made sense at that time. https://hbr.org/2017/05/whats-your-data-strategy
        - 2. I was already exploring data-ownership and data-as-product from zamak dehagni's data-mesh
    - parallely, there were some good stuff on ETL time reduction with aws-glue jobs from one of the exiting team
    - I did make some fail attempts to strategize the static-data(master-contractual-data,master-product-data)
    - Finally, I proposed a theory, that all the product-lines could be decentralized and isolated so that they could be scaled horizontall or vertically as per the future data-volume growth. Gave some techineques of cloud-object-store options, its partitioning techniques, these were all nosql-solutions. So its hard to convince anyone, unless they have done it.



- [My Quick Bites on Problem Solving](#my-quick-bites-on-problem-solving) | [Math Works](#math-works)

- My Take on :  [Software Design](#software-design) | [A Bit On Software design](#a-bit-on-software-design) |[Design Principles](#design-principles) | [Patterns](#patterns) | [Domain Driven Design](#domain-driven-design) | [Data Modeling](#data-modeling) | [](#system-thinking) | [System Thinking](#system-thinking) | [Software Architecture](#software-architecture) | [Cloud Computing](#cloud-computing)
[Execution Style](#execution-style) 
- [My Java Stack & Few Titbits](#my-java-stack--few-titbits) | [Fascinating Technologies](#fascinating-technologies)  | [an-engineer-since-2019](#an-engineer-since-2019) | [Execution Style](#execution-style) | [Teaching Mentoring](#teaching-mentoring)
 | [](#) | [](#) | [](#) | [](#) | [](#) |


## Company-3-Wipro Apr-2016 Jul-2018
### project-1 (Ericsson Account -  Telecom)
- Configuration Service - Library
- my-role : started as senior developer, eventually taking lead of all major features, enhancements and support
- purpose of appication: a central library for all 50 plus hosted [OSS Telecom](https://en.wikipedia.org/wiki/Operations_support_system) aplications to talk to database([Versant Object Database - VOD](https://en.wikipedia.org/wiki/Actian_NoSQL_Object_Database)), it  had abstraction for below
    -  2-phase-commit transaction 
    -  a primary publisher to event-channel, publishing all events from 50+ applications which connected to VOD
    - Some OSS configurations, adaters(MIB,RAN) etc
    - built on top RMI, CORBA for few appoications
- a-little-story-to-share :  The team was good, our scrum-master cum manager called BABA protected us from unnecessary issues, I also got work with a colleague-1 a domain expert on telecom with a decade of expericence, he always had an idelology to fail-fast and fail intelligently, may be becasuse of the issues seen around. There was another colleague-2 who had become a SME in our space  with solid exposure in administration of versant databse and shell scripts and he was really good at articualting things to customer Ericsson.
Primarily, we 3 for almost 1.5 years, as an ally guarded the fort of CS libary from all the support activities be it quarterly tussle of ST-KPI, deadlock-support, rollback of transaction etc , from 50 plus applications we could literally get ticket from any where, any team. There was this ball-game of its not our issue war from the raiser. Some issues were so wierdly raised, support wasn't even needed and mostly we had to diplomatically handle the support tickets, which my other two colleagues excelled with command on the OSS domain and I generally took the technical-research and piteched whenever deeper code, design was involved.
- Though designated as architect in wipro coming back to my contribution my first  recognition / reputation didnt come for solving/troubleshooting issue, but ti  was for improving a consisteny-check-tool(usually-took-50 mins) which i improvised(reduced 15 to 20mins) by recuding system-calls, networks-calls, io-calls. probably my colleague-1 wanted to check my approach
- the frequent issue , when the ticket was raised  was cs library has locked the transaction, we need their support, it was optimistic locking strategy which every application could have chosen when they connect to CS libary, but they needed our help to show that, since two application concurrent behaviour for data-integrity lock could have occurred, there was blame game for lack of knowledge stating application A, B...X caused it etc,
most of the time my-allyteam(myself,colleague-1,colleague-2) we suggested you just suggested you retrigger your usecase because thats what is needed to do, some teams were adomant(stated) to give full explanation, so we took the global event-channel log it gave applications A,B,..x who caused, the sharded resource(object) on versant-database etc they never came back after that mail,ticket comments not sure what they understood.
since I was a new commer my colleague-1 and 2 did many times articulation because i spoke too much technical digging into versant database source occassionally, JTA etc give clarity.
- there was 1 one more ticke of special interset , some application team came and said that CS libary the comment section of resource(RAN,WRAN,MIB etc) is limited and we could enhance it to be unbounded length. I was just thinking did he mean ram size or hard disk size. my colleague-1 said to take a look, i said we could go max ram size or the string's size not beyond that. He said please gather some proof for your statement then i researched at both jvm and Javalanguagespec. then recalled java-source code String class and its length method backed by char[].lenth, gave proof that that max, gave apporximat 2^32 -1 . My colleague-1 took this info and handled ticket on this own taking out the complexity which the application team x had raised.
- there were few more enhancements which i did, if i recollect will add later
- ### Reason to leave
    - 2 years was quite a stretch, for a project which was getting decommissoned, getting release from project also felt trickier, so quit to look for new opportunities hoping for exposure in microservies, cloud. Also took a break, 1.5 month or so hoping to join a product-based-company
- some intersting observations to debate or discuss or improvise
    - This was my first exposure to consultancy services  from office , canteen, campus etc. It was a very unique experience on campus, culture
    - Ocassionaly looking at source code of projects, I could literally see GOF patterns, few J2EE patterns, EIP, it was built very beautifully with separation of concerns with just plain java classes and structures, probably the best crafted code so far in my experience, excellent test coverage etc. It was a decade old, very stable. Hoever it was in getting decomissioned in next couple of years, probably for 5g push with new tech-stack of microservices, containerization backed by  neo4j but it happend in Ericsson, Ireland
    - I also got  introduced into a concept of rooster-call on-call-support for weekends. This was the reason I got my first laptop, till then i was only working on desktops, so had to go to office, In wipro also remote work meant only for weekend support, even with laptop u still had to go to office for ericsson account on weekdays.
    - a very seriously annoying thing for every release  was something called ST-KPI, it was metric to measure if there was delta in performance between (previous, current), thats a big story, if performance impoved/degrade we had to findout root-cause, not sure who devised but they did forget the jdk upgrade, ant/maven upgrade, os changes, database upgrade etc, it was a big mess all together finally someone top all way to ericsson client made a decision which benchmark to be taken going forward which i never got visibility.
    - on fun side post lunch, we were a good team of 7 to 8 people , though not directly connected on work, but belonging to same restricted area, we enjoyed food, conversations, gossips and a 15 to 20 min walk.
    - left wipro on 11 july 2018,  with a cake celebration(first one for me on leaving company)

   
## Company-2-CSC Dec-2009 to Mar-2016
- CSC Computer Sciences Corporation, now DXC again acquird by HP
- Tenure 6 years: attempting to be a good consultant, exploring leadership, collaboration, new challenges in domain of telecom,investment-banking
- ### Client-1 : Verizon Data Services
    - tenure : 3 
    - project-1 : Vmlite(verizon mobile lite) field technician app, taste of blackberry with perstdb
    - purpose : The blackberry application was primarily targed for verizon field technician for routine FIOS installion, repair work, backed by scheduling, job assignment, gps-tracking etc.
        - on a side note, i never tested the app on real blackberry app, occasionaly verizon colleague demonstrated to us. we did everything to the best of our imagination on a simulation IDE on our PCs. It was good enough, occasionally for some UI distortions we had to see real screenshots of user tickets
    - my-role : joined as a consultant developer, occasionally took lead on development, as per the autonomy, as given by my verizon-client-manager after a years of trust. Although, I would like to make a special mention of my csc-colleague-1 with whom I devised several solutions. Before joining CSC to work with me, he had prior experience on verizon-domain, he was a ex employee. 
    - my tasks, contribution
        - semi-automation-1 :  
            - a-little-story : A good one to share, as I was tasked load some static-data to database and devise a solution (automation-script), the static domain was little tricky, it was basically all static data of field technicaian blackberry app GUI controls like drop down, choices, labels etc. These were supposed to be dynamically loaded in several screen of blackberry app.
            With a dedicated week of effort,  I was able to  devsie a partial solutiong in java, parsing and reformatting with something like notepad/textpad which i dont recall. I loaded all data and went back after a week or so, to my client-manager, I had streched late-night to acheieve this, not to impress or get  recognition, it was difficult to split the work i was trying to automate. one of the expert, saw, verified the work and said good work. For me it was till then, intersitingly every day afternoon my other CSC colleague used to send a mail stating i will be late to office.It was larger audience in the mail chain. My client manager, seeing that work was completed faster than his anticipation, relaxed me coming late to office. And asked my other-csc-colleague not to publish my late coming mail. There were multiple things later I built on top of this
        - automations-2-gps-location-updater: another feature  to share the location silently every time a feild-technician picked a job, dida a status-update, reroute, etc . I implemented using a timer logic with explicit control on timer settings etc.
        - automations-n : I did build lot of blackberry screens, though there wasnt a sophisticated like java swing, some box layouts helped as I recall. Ofcourse due to limitations, blackberry ram and perst OO db, lot of tweaking was needed, so occasionally to save memory, I did leverage some binary arithmetics ocassionally for storing data.
            - then it went on bug fixing, feature enchancements, i became approachble on blackberry front end developer.
        - 
    - project-2 : vmobile laptop app
    - Purpose : The requirement was to build a laptop desktop application, probably few fields technicians were getting/promoted to use laptops for their work. A team from US, who was heading , wanted to resuse the existing business domain logic and build a a new application which was almost similar/tobe-faimilar wth blackberry application.
    - challenges : 
        -  an alternative vmlite blackberry app meant that we need get familiar with pretty much all the screens.
        -  a juggle of reusing vmlite's business logic, the extensive optimized code and its relaxation to huge Java heap memory, though a big relief, we had to rewire lot of java code. 
        - blackberry app fully blow into laptop meant lof  plenty of real-estate, what do we fill with.
    - my-role : along with my csc-colleague-1, a key developer, then occasionally, leading front-end-development as per the autonomy-given. 
        - Filling plenty for real esate with useful stuff for technicians came to my cup of tea. Now the company-1-Tomax experience of experience came for my help, including protypying approach of CXA, I too demonstrated some clickable dummy screens, so that US team could feel it in first hand.
    - my tasks, contributions :
        - an-intersting-story to share :    I was a natural pick, with Swing in my expericence,  I proposed, we should be building adaptive screens, and we could incorporate little extra developemnt time for building resualble table component promising reduction of future developemnt time. It was a bit to struggle to convince the stakeholders especially US team.     Luckily, my csc-colleague-1(now-a-long-term-friend-of-mine), had prior experience in verizon and quite reputation. So he convinced on our ideas. While I was in full tracktion of leading on the front-end technology, he took care of back-nuiances like a soap webservice, polling etc. and he taught few of this to me as well, while I taught him few things on Java swing techniques.
            - a funny and intersting thing based on abstraction of reusable table component i had built, he leveraged them and to everyones suprise, he built almost 5 to 7 screens in a week or so. Ocassionally on his backend code, i got to fix few bugs or enhancements. We were a combination to crack anything we were thrown at.
            To make use of entire real estate i used several techinques like
                - column widths could be expanded to the frame of desktop, i had backed everything to gridbag layout, border layout management
                - i dont recall fully, but i vaguely suggest that we gave lot of options and embedded several useful components, becuase we had too much real estate, say like going from 1-rk to a villa design
           Eventually with few demos and promise of new capablities, slowly it got statbilized. and after few months of production, we got to hear that its lot easier for field technician on laptop then blackberry due to screen size and extra capablities which we had introduced. 
        -  automations-n
            - for first time , I had applied multisort thing on tabular data.
            - serialized entirire object graph, make a deep-clone copy , so that application preferences for field technicians could be save on log out to disk of laptop. on laptop the field technicians prefrences were restored.
                - I also recall that, field technician technician could take a screenshot of job buckets, etc, for which again above serialization was used on jtable view, but not on actual tablemodel by leveraging java's tranisient variable feature.
            - mostly I we 
    -  some intersting observations to debate or discuss or improvise
        - Lessons learnt, you need a strong ally(my-Csc-colleague, client-mgr, client-team-lead), to make sure your/our ideas work.
        - dormitory : I usually went to client office late, they were least bothered on when I went, rather on my transparency and efficiency of my work. So many times initially, I did sleep in the office dormitory. some times i even took powernaps during lunch times. Every office if affordable should have one I feel.
        - we had lot of good conversations with verizon colleagues, I was also quite notorious on debates on pretty much any topic and prett much many were getting entertained on our evening tea breaks full of tamil,english context switching conversations.
        - few things you encounter  as being consultant for first time :
            positivies : we  could finish one project, move on to another one, probably for those who want to be more technology-centric and aspire to learn or get into new challeges.
            downsides : there were some tiny things like as a consultant, i wasnt not allowed to go to verizon-specific things like  lunch, team-outings, townhalls, internal-demos etc a kind of first experiences. this varies org to org, but something to know or be familiar with
        - every-weekend-travel :  every friday I use to travel to bangalore from chennai and by monday noon i was back to office.
        - sometimes, we all were asked to come weekends, I usually got saved from my hectic every-weekend-travel
- ### Client-2 : VISA, CSC (2 months)
- VISA
- it was hardly 2 months, it was on decommissioned state and moving to fully l3 support model, so I moved on, 
    -  on a side note there were some credit card processing domain session by an excellent BusinessAnalyst, that was helpful
- project-3 (referential repository)
- ### Client-3 : Societe Generalle  
    - Domain : investment banking (referential-asset, booking-keepin on trade movements)
    - Tenure : 3 years,  
    -  special-mention : Societe Generalle,  my goto company-name, for open-culture-with-transparency, 
    - project-1 : 
        - purpose : to consoldiate all the stocks/instrumens data and treat as golden copy for downstreams. 
            tech-stack : a proprietary asset-mgmt-tool desktop application , backed by tibco rv messaging, ant builds, oracle db 
                - running simple 
        - my-role : as a developer(desktop,backend)
        - my tasks, contibutions
            - automation-n :
                - some enhancement on screens with asset-mgmt-tool, bug fixing
                - enhancements on message filtering, 
                -  did ant to maven migration(1000 of scripts floating) did some bash scripting to automate work, had to incorporate/inject backward compatiblity  stuff like that.
    - some intersting observations to debate or discuss or improvise
        - a very good team lead, superb BA, QA and excellent team members, I never felt like a consultant
        - on a side note our client team lead ensured that we all go around 4 evening for a tea-break and no technical discussion. We could freely talk anything, random discussions.
    - project-2(securities-book-keeping) officially my first web-api development with soap-services, prior to this it was all servlet/jsp/jsf
        - purpose : As I recall, there separate applications(securities-book-keeping) for each market region like frankfurt, luxemborg, Societe Generalle was planning to unify all those with a single application. Seurities based geography were tobe reconciled from  the position/movements for each trade done for that particualr region/market
            -  pralllely  upgrade with an existing tool with latest technogies and some new business capabilities
        - my role : key backend developer, along with occasional frontend app development.
        - my tasks designs, contribution : 
        - automation-1 : Bancs CA Initialization tool
            - Led the key design of web services on Bancs CA Initialization tool, built a reusable workflow algorithm which did aggregation of thousands of positions/movements of stocks. me and france conterpart BA, we ensured all critical business use case were covered and even did  a manual load testing for some extreme figure. Basically the BA did all load testing
            I had backed the whole aggreagation logic with heavy use of bottom up tree building, leveraging hashing. To the best tof my knowledge I kept scalablity in my mind ensuring  statelss with soapful-webserices. Also, some key domain tables in database had billions of rows, so i had pulled all the data for my use case and did aggregation applying business rules in java-memory.
            Even 1 decimal variation was unacceptable. This was my officially first encounter for building scalable web apis and with some good success. This has been very instrumental and foundational experience  for all of my scalable distributed computing so far. I just got better as I got to compute further on large data sets.
        - automation-2 : Bancs Trade Update workflow
            - Designed real time Bancs Trade Update workflow of ISI, I had built an good abstraction some good parts which  I had built above to efficiently  update the trade workflow data.
        - Tuned a performance issue on security integration taking 10 min to less than a minute, related to dependency injection, 
    -  some intersting observations to debate or discuss or improvise
        - culture : unlike verizon, societe generalle had very open culture be it lunch, team-outings, townhalls, internal-demos etc a kind of first experiences being a consultant. Except for the fact that i got paid from my CSC, everything in societe generalle was equal treatment for all. No laptop for anyone. A strict policy of not working beyond 7pm, pretty much deserted. There were rumors that if anyone worked late continuously, then the manager gets call from HR, to check on overburn. In entrie 3 years tenure, that I on my own went a weekend for few hours, due to a deadline and my own commitment and cracking of some business rules and devising algo.
            - I was tasked to take several interviews, even for societe generalle employees
        - I predominantly worked with  2 BAs who had extensive knowledge and were open enough to simplify the domain of how trades happen. one of them prepared an excel , priortized the use case, i kept on building stuff as per his instructions, correcting my aggregation logic , we even tested for a scale of few 100 thousands , which BA tested and passed. These two BAs were from France, so occasion we shared a lot of our cultures, food.
        - true agile : we synchronized our scrum calls with france-team post lunch and the france-team very good at task-estimation-6h-rule, assingmet, live update of status in JIRA, if you committed to a task, you had to deliver, neither over/nor under estimation was allowed. So we split several tasks for a day. This was a big learning for me as well. 
        - biggest-takeaway : I got convinced that stock market is trustable and  I can also invest. So its a life time lesson added for my financial-goal. As of now, this is also a retirment plan of mine.

## Company-1-Tomax Jun-2005 to Sep-2009
- Tomax India,Bangalore 
- Domain : Retail
    - Exposure on inventory-mgmt, workflow-mgmt, merchandise-hierarchy
- Tenure :  4.3 years, taste of good-developer caring-for-performance, building-reusable components for desktop-applications, prototyping-on-domain-flow, 
- Tomax, had some catchy phrase - demand-driven-conntinum, connecting-the-dots
- ### project-1 
    - New Promo UI (Revenue Management) 
    - Purpose : A new Desktop application with new business capabilities and flexiblities for managing promotions to extend the reach to new parteners and customers.
    - automation-1-SKU-Lookup-Screen: 
        - role - frontend-developer
        - My tasks, contributions
        - my-first-developement-story :  I was tasked to build a inventory lookup screen using java swing desktop library, it went for several weeks to shape it up, wrote thousands of lines, mostly fear of bug, wrote lot of defensive code on 1 side, embedded lot of flexibilty for user to search with anything like substring, combination of domain-fiedls like item, category backed by sql options (or, like, %)  and few on java-layer, i introduced lot of configurations for explicitly controlling the behaviour. of course pretty much lot business rules on event-listeners.
        Had also built quite a bit of  abstraction keeping MVC(push-model) using  JTableAbstractmodel, JTable-view , configuring column-heards even to populate the results of search. The result them selves were sortable based on the click of view etc. The work had also got 
        delayed for few weeks, however got support from my team-lead-cum-mentor, having convinced him on with expalination of all what i was trying to embed. Ofcourse there were few bugs and the search screen was well received, i got some fame from it as well.
        Though i was little skpetical on working java swing building graphical components, its my team lead/mentor who encouraged that its a good way to start the career.
        - automations-xyz
            - ofcourse I built lot of screens, enhancements, fixed bugs etc, which I dont recall much
    - some intersting observations to debate or discuss or improvise
        - I became  very good on layout managment with adaptive behviours, especially using gridbaglayout manager, because it had weights to strech a component in both horizontal and vertical dimension. Till date I leverage this techniue on several ways, yes it as something to do with even LLMs 2B,70B models as well if you think interms of weight.I also got expertize on building table, table tree ui components. This helped for almost for next 6 years or so until i completely switched by profile for backend-developer.
        All amazing stuff i did was because of math of building adaptive screens irrespective of display-device size.
        Of course lot goes to on my java OOPs concepts to build reusable components and few  j2ee patterns but it wasnt visible to everyone, because the frontend work I did overshadowed.Then i kept on building several screens, reusable components as I got assiged to multiple projects.
        - slowly, though I was famous for front-end developement, i got great interset in backend using jdbc, hiberante, ejbs, servlets, jsps etc they were trending at  that time.
        - Sadly, I had to move away from my mentor's direct coaching, but we kept connecting whenver i got struck for my entire tenure of Tomax, even for next switch of my company
- ### project-2
    - workflow-activity-management, Time and Attendance
    - Purpose : 
    - automation-2-merchandise-hierarchy
        I vaguely remember that we had to build a screen where in we had to list all retail stores  revenue for its respective HQ.
        - My mentor had already taught me building tabletress in my project-1 which came handy here. It was the probably the most interesting component I built with java swing. At tree you display HeadQuarterStores and on click of it we had to pull all the store which were assigned to it. As i vaguely remember technically I had solved it by using a 10 level hashmap anticipating the depth backed by custom tree data structure with typical node referncing itself with parent and children, the table model computed overall aggregation and rolled up to its HQ. 
            - on a side this technique I have leveraged has been a life saver in many of my developement till date. 
    - automations-xyz
        - ofcourse I built lot of screens, enhancements, fixed bugs etc, which I dont recall much
        - This project had lot of different tech stack with  workflow-domain(Portlets, Struts, Shark Enhydra Workflow) backed by ejb, hibernate servlet jsp etc
        - it was lot of quick dirty works of servlet/jsp combinations fixing bugs, 
        - again built several resuable components, got to collaborate with different team-lead they had different ideologies, but I continued with my initial teachings of my mentor. after a year or so this project was called off, we did everything best, amazing stuff, etc but got to hear there end user vision had changed. Lesson learnt , validate the business requiremnts, so hence forth till date i strongly apply domain-driven-design and validate business-requiments, probably strong reason of [Why do I step into your shoes](#why-do-i-step-into-your-shoes) ideology
- ### project-3
    - CXA   customer-experience-architecture for [Les Schwab tires ](https://www.lesschwab.com/) 
        - on a side note , myluck its business still contines but the appointment scheduler is not what we built, definitely front end technology change every 3 to 5 years that to blame
            - however the factors for booking appointment like tires(new, flat repair..), serverices-like(brake, wheels, alignment) followed by date and slot options are pretty much striaight forward, a strong reason for advocating/my bias on DDD
    - Purpose : To build a tire service desktop application for services like appointment, MRO-stuff, sale of parts etc
    - my-role : lead developer in tomax-india, training coaching
        - a-little-story : back then it was 2008 to 2009, housing bubble, Tomax apart from its retail-product-suite wanted to experiment on services, so  Tomax US had visioned a new architecture a prototype baseed apprach, called by CXA-Customer Experience Architecture. This was very new experience where we got see some plain screens with button and navigation you could pretty much experience the whole flow. probably true new agile methodology for me. 
        Now there was one key change on tech-stack, for front end they zeroed on RIA library ULC . Unlike java swing , this was server side technology. The desktop GUI components were half-client half-server(backed by RMI if i recall). Primarily there were two people we had strong grip on building desktop application my mentor and my self. And on US counter part i heard there were two developers leading this whole program (surpisingly they were almost near to 60 years of age. This was a useful information, i got to learn that i can become a developer till 60 years of my age). Thats how I became lead developer not by designation.I  got training from  my mentor and those two super senior deveopers.Now i was tasked to train others including my other tech-leads who were leading web development projects.For tomax this was the most visible project, because as opposed to reatial-product they wanted to try services for this 400 store Les-schwab Tires. Now i was also in limelight, not the technology was hard but i had to train and work with almost 2x to 3x of my experence, I betted on my grip on java, swing libaray concepts, knowledge on ULC and trained many for 2 months, sharing all the knowledge I had.
    - my tasks, contribution
        - When project started i did something different in execution.I took lead on few critical component(appointment-schedueler, reusable-table-comonent,reusable-tabletreecomonent), and guided others on their day to day development acitivities. Anybody could grab me for anything they needed on ULC. of course lot And lot went smooth, Ocassionaly I had guidance from my mentor and other leads when i was getting struck.
- ### Reason to leave, Tomax
    - It was mid-2009, we recived a letter from CEO stating "Nothing is permanent in life" and  ending with we are closing Tomax India operations. More than me, it was shocking for several seniors as probably because of their financial dependency, emotional attachement(including myself).on sep 15 2009 we all tomaxians-India were happy, because we got almost 4 to 6 months of salary as compenstation based on tenure we served. I just said to myself any company i join, i will keep resignation in my pocket and work hoping termination from either-side any-time.
    - i took a break to spend 2 months with my family, went to my native for  a month enjoying food. Then when i started back, job openning were little less, more screening due to global financial housing bubble impact. Finally, after a bit of struggle, with 50% hike i got an offer from CSC, chennai, i accepted
- ### Few interesting stories to share 
    - story-1-double-training : I wasnt smart enough to get a college placement, so did a Java/J2EE course from [NIIT](https://www.niit.com/india/java-full-stack-developer-program) and from its placement, I got into Tomax. Here again I was on a further training of 6 months, re-trained on java,sql, dbms concepts, html,javascript and retail-domain as well. Along with me, Tomx had hired 3 more from diffrent NIIT branches. We  four all-new peope from NIIT(different branches), different states got four mentors who trained extensively  abased on real experience. Parallely we were tasked to build a software library for the company. Though initially were bit of competing coming from different regions,states,languages culture, we slowly adopted  towards just 1 goal building the library and our goal, to the best of our knowledge making the library  more usable  for company users.  And we were the first pilot batch which tomax was experiment on an idea grooming freshers vs hiring exprienced ones and grooming. Initially, we gave test 1 in each month, for 3 times i recall. This was foundational for strenghting in my OOP concepts, java, multithreading concepts also how to work in collaboration. also a little on my leading and presentation skills. For Tomax, it our pilot batch was success
    - story-2 :  when I first got into a project-1, i was tasked to do testing for 3 weeks or so, i was little skeptical as i wanted to start on development, coding-stuff, i did research on wiki narrowed that boundary testing is what testers fail from database,  having looked at database constraints i was able create few bugs in Jira to everyones surprise. later i got to know that that the  scenario(business-flow) never happens. 
- some intersting observations to debate or discuss or improvise
    - CXA technique : I did leverage this prototype based apporach in my future projects especially in Verzion while buidling field technician application to  build stuff and adapt based on rapid feedback. This was a phenomenal technique i used for almost all of my front end development, later when  I switched to backend-profile, it helped me understand better on api contracts with web-services(SOAP, REST) like building dummy/static APIs structured with  static-data representing with few core business use cases 

