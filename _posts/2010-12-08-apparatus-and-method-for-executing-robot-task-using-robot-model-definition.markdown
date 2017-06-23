---

title: Apparatus and method for executing robot task using robot model definition
abstract: Provided is an apparatus for executing a robot task using a robot model definition. A task execution apparatus include: a storage unit to store at least one robot model, at least one robot behavior, and at least one robot task; and a task execution unit to generate at least one execution object from the stored at least one robot model, at least one robot behavior, and at least one robot task, and to execute a task of a robot from a corresponding execution object among the generated at least one execution object in response to an execution command input from a user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08588973&OS=08588973&RS=08588973
owner: Electronics and Telecommunications Research Institute
number: 08588973
owner_city: Daejeon
owner_country: KR
publication_date: 20101208
---
This application claims priority to Korean Patent Application Nos. 10 2009 0127079 and 10 2010 0052035 filed on Dec. 18 2009 and Jun. 1 2010 respectively the entire contents of which are herein incorporated by reference.

The present invention relates to a robot interface technology and more particularly to an apparatus and method for executing a robot task that may execute a robot task using a world model definition of a robot.

A conventional scheme of describing a task in a robot or a machine includes a scheme of describing a task using a programming language for example a programming language such as c c or a description scheme of expanding a syntax for task execution to an existing programming language.

When using the programming language such as c c there are advantages in that a unification with an external application programming interface API is convenient a variety of functions provided from c c may be easily included and an execution speed is fast.

However in the case of such task description scheme a describer should directly describe all the tasks performed by a robot through programming and thus an amount of programming may considerably increase and modification and update of tasks may be inconvenient.

To overcome the above drawbacks a scheme of describing a task using a robot exclusive task language has been proposed. However this scheme needs an interpret unit that can define and interpret a syntax of task language and thus a configuration of the robot becomes complex.

The present invention has been made in an effort to provide a robot task execution apparatus that may execute a robot task interoperating with various robot application programming interfaces APIs using a robot model defined by a user.

Further the present invention has been made in an effort to provide a task execution method of the robot task execution apparatus.

An exemplary embodiment of the present invention provides an apparatus for executing a robot task the apparatus including a storage unit to store defined at least one robot model at least one robot behavior and at least one robot task and a task execution unit to generate at least one execution object from the stored at least one robot model at least one robot behavior and at least one robot task and to execute a task of a robot from a corresponding execution object among the generated at least one execution object in response to an execution command input from a user.

Another exemplary embodiment of the present invention provides a method of executing a robot task the method including generating at least one execution object from and stored at least one robot model at least one robot behavior and at least one robot task and executing a task of a robot from a corresponding execution object among the at least one execution object in response to an execution command input from a user.

According to the exemplary embodiments of the present invention an apparatus and method for executing a robot task may provide a user with convenience of a robot task technology by executing a briefly defined robot model a robot behavior or a robot task according to an interpret unit scheme regardless of a user robot API. Also the user s frequent modification update and the like with respect to the robot task may be enabled.

The accompanying drawings illustrating exemplary embodiments of the present invention and contents described in the accompanying drawings should be referenced in order to fully appreciate operational advantages of the present invention and objects achieved by the exemplary embodiments of the present invention.

Hereinafter the present invention will be described in detail by describing exemplary embodiments of the present invention with reference to the accompanying drawings. Like elements refer to like reference numerals shown in the drawings.

The apparatus unit may include various apparatuses mounted in the robot system for example a sensor and an actuator . An operation of the apparatus unit may be controlled according to a control signal CNT output from the task execution apparatus .

The sensor may output a sensing value according to operation of a robot. The sensor may be a sensor for sensing a location of the robot such as an acceleration sensor a direction sensor and the like or a sensor for sensing an environment where the robot is located such as an ultrasonic sensor an impact sensor a tactile sensor an imaging apparatus and the like.

The sensor may operate using a predefined sensor application programming interface API . The sensor API may be distributed from a manufacturer of the robot system .

The actuator may control the operation of the robot. The actuator may be configured as a driving apparatus such as a servo motor and the like.

Also the actuator may operate using a predefined actuator API which may be distributed from the manufacturer of the robot system .

Referring to and the storage unit may include a model storage unit a behavior storage unit and a task storage unit .

A variety of robot models MD defined by a user or a task writer may be stored in the model storage unit .

In this case the user may define the plurality of robot models MD using a plurality of APIs provided from the apparatus unit for example a sensor API or an actuator API.

In addition the user may randomly define the plurality of robot models MD using a physical or logical recognition target recognized by the robot and a variety of information obtained from the physical or logical recognition target.

Referring to and the user may define a robot model MD based on a plurality of APIs obtained from the apparatus unit or random information.

A single robot model MD may include a plurality of models. illustrates an example where an obstacle detection model an arm motion model a voice output model and a wheel movement model are included in the single robot model.

Here the function and the symbol may correspond to means for obtaining information from an outside the action may correspond to means for defining a behavior of the robot and the displacement may correspond to means for defining a variable.

In addition the state may correspond to means expressed as a logical expression equation using the function the action the displacement and the symbol of the model. For example in the arm motion model of the state of arm.elbowUp may define a state where an arm of the robot is up using the function of getCurEblowAngle .

In the meantime the user may define a new model by combining at least two models. For example a taskCtx model of may be a model defined by combining the obstacle detection model and the wheel movement model. A taskCtx.controv context included therein may define a circumstance where an obstacle is detected while a wheel of the robot is moving.

Referring again to and a plurality of robot behaviors BH defined based on the plurality of robot models MD by the user may be stored in the behavior storage unit .

For example in robot behaviors BH called bhv and bhv are defined. It can be known that each of the robot behaviors BH is defined based on at least one model within the predefined robot model MD.

Each of the defined robot behaviors BH may include two portions for example a decision and an activity.

The if function statement included in the decision may be written using a function a displacement a symbol state and a context model of the robot model MD however an operational model of the robot model MD may not be included.

The activity may be defined to control an action of the robot when a particular condition is satisfied in the if function statement of the decision.

The activity may be included in the decision or may be separately defined. illustrates an example where a plurality of activities are separately defined in a single decision.

Each activity may be written using the function the displacement the action the symbol the state and the context model of the robot model MD. Each activity may include a value allocation statement a parallel execution statement an if statement a function call a behavior call and the like.

For example in robot behavior bhv defines a single decision using three if function statements and defines three activities performed when the respective corresponding if function statements are satisfied.

Accordingly in a case where the robot behavior bhv is referred to when a task is executed by the task execution apparatus a corresponding activity may be executed by determining whether the three if function statements of bhv are sequentially satisfied.

Also when none of the three if function statements of bvh are satisfied a separately defined robot behavior bvh may be executed. Even in the defined robot behavior bvh the corresponding activity may be executed using the same scheme that is a scheme of determining whether an if function statement is satisfied.

Referring again to and a plurality of robot tasks TS defined based on the plurality of robot models MD by the user may be stored in the task storage unit .

For example in it can be known that a robot task TS is defined using a taskCtx model of the robot model MD.

The robot task TS may be defined using a single repeat function statement. The repeat function statement may include an if function statement.

Specifically the robot task TS of may be defined so that a predefined robot behavior that is a bhv behavior may be performed until a taskCtx.targetPerformed variable is true.

Here a repeat condition of the robot task TS may be defined to be performed when a single activity of the robot behavior BH is executed.

Referring again to and the storage unit may output a stored plurality of robot models MD a plurality of robot behaviors BH and a plurality of robot tasks TS to the task execution unit or the binding object according to a request from the task execution unit .

Referring to and the binding object may generate and output a dynamic library DLL that may represent a value of the robot model MD from a template code TC that is provided from the task execution unit . The task execution unit will be described later.

The code generator may generate and output a model code MC from the template code TC that is transmitted from the task execution unit .

For example the code generator may generate the model code MC using a scheme of filling inside the template code TC based on a variety of APIs input from the user or random information and the like.

The compile unit may generate the dynamic library DLL by compiling the model code MC output from the code generator .

The model binder may output to the task execution unit the dynamic library DLL generated by the compile unit according to a request of the task execution unit.

Referring to and in response to a user command CMD input from the user for example a task execution command the task execution unit may extract a single task from a stored plurality of robot tasks TS and may execute the extracted task.

In this case the task execution unit may execute a robot behavior BH or a robot model MD associated with the extracted task.

The task execution unit may include a parser an object generator an object storage unit and a task interpret unit .

The parser may parse and thereby output the stored robot model MD the robot behavior BH and the robot task TS stored in the storage unit .

In this case the parser may inspect an error of the robot model MD the robot behavior BH and the robot task TS and may also perform a parsing operation according to an inspection result.

Also the parser may generate and thereby output a template code TC for binding with the aforementioned binding object .

The template code TC may be a basic code generated to obtain a model value of the robot model MD and may be generated based on the parsed robot model MD.

The object generator may generate an execution object OB from the parsed robot model MD the parsed robot behavior BH and the parsed robot task TS that are output from the parser .

Here the execution object OB generated by the object generator may be an object defining a class of the robot behavior BH or the robot task TS.

The object storage unit may store at least one execution object OB output from the object generator .

In response to the user command CMD input from the user the task interpret unit may extract a corresponding execution object OB from at least one execution object OB stored in the object storage unit and may execute the extracted execution object OB.

For example in response to the user command CMD the task interpret unit may extract the corresponding execution object OB from the at least one execution object OB with respect to at least one robot task TS stored in the object storage unit .

Also the task interpret unit may execute the execution object OB with respect to the extracted robot task TS. In this case when a model value of the robot model MD within the execution object OB is required the task interpret unit may receive a dynamic library DLL from the model binder of the aforementioned binding object .

In the meantime although not shown in figures the task execution apparatus may further include a task manager. The task manager may control an operation of the task execution unit by interpreting the user command CMD input from the user and may manage the execution object OB stored in the object storage unit .

Referring to through a user may define a robot model MD a robot behavior BH and a robot task TS using a plurality of APIs or random information. The storage unit of the task execution unit may store the defined robot model MD the robot behavior BH and the robot task TS S .

The user may initially define the robot model MD including at least one model and then subsequently define the robot behavior BH and the robot task TS using the defined robot model MD.

Accordingly the defined robot behavior BH may include at least one model of the robot model MD and the defined robot task TS may include at least one model of the robot model MD or the robot behavior BH.

The task execution unit of the task execution apparatus may parse the defined robot model MD the robot behavior BH and the robot task TS S and may generate an execution object OB from a parsing result S .

The parser of the task execution unit may obtain the robot model MD the robot behavior BH and the robot task TS stored in the storage unit and may parse and thereby output them.

In this case after a user command CMD is input into the task execution apparatus from the user the parser may obtain from the storage unit and thereby parse the robot model MD the robot behavior BH and the robot task TS corresponding to the user command CMD.

Also when each of the robot model MD the robot behavior BH and the robot task TS is defined by the user and thereby is stored in the storage unit the parser may also obtain them from the storage unit and thereby parse.

The object generator defines a class of each of the robot model MD the robot behavior BH and the robot task TS from the parsing result that is output from the parser and thus may generate the execution object OB. The generated execution object OB may be stored in the object storage unit .

In the meantime the parser may generate a template code TC based on the obtained robot model MD and may output the generated template code TC to the binding object S .

The binding object may generate a model value that is a dynamic library DLL with respect to the robot model MD based on the template code TC that is output from the parser S .

When a request is received from the task interpret unit the model binder of the binding object may output the generated dynamic library DLL to the task interpret unit .

In response to the user command CMD input from the user the task interpret unit may extract a corresponding execution object OB from at least one execution object OB stored in the object storage unit .

Next the task interpret unit may execute a task desired by the user by executing the extracted execution object OB S .

In this case the task interpret unit may execute a robot task which the user would like to execute by executing a robot task TS included in the extracted execution object OB that is a robot task TS defined by the user.

In the meantime when the task interpret unit needs a model value with respect to the defined robot model MD while executing the execution object OB the task interpret unit may receive the necessary model value that is the dynamic library DLL of the robot model MD from the model binder of the binding object .

Hereinafter the aforementioned task execution operation in the task execution apparatus will be further described with reference to .

Referring to through and in response to a user command CMD the task interpret unit of the task execution apparatus may extract a single corresponding execution object OB from at least one execution object OB stored in the object storage unit and may execute a robot task TS within the extracted execution object OB.

In this case the robot task TS of the extracted execution object OB may include a plurality of syntaxes that is a plurality of statements. Also a robot behavior BH or a robot model MD of the extracted execution object OB may include the plurality of statements. At least one function statement may be included in a single statement of the robot task TS.

The task interpret unit may read an initial statement from the robot task TS of the extracted execution object OB S .

In this case the task interpret unit may determine whether the read statement is calling a behavior of a robot that is the robot behavior BH S and may execute the robot behavior BH associated with the statement of the robot task TS S or may execute the statement of the robot task TS depending on the decision result S .

After the statement of the robot task TS is executed according to the decision result the task interpret unit may determine an order of the executed statement within the robot task TS S .

In this case the order decision of the executed statement within the robot task TS may be omitted depending on embodiments.

When the executed statement corresponds to a final statement of the robot task TS based on the decision result the task interpret unit may determine whether the executed statement is repeatedly performed S .

For example the task interpret unit may determine whether a repeat function is included in the executed statement.

In this case when the repeat function is included in the executed statement the task interpret unit may determine a termination condition for example whether the executed statement satisfies the repeat function S and may repeatedly perform the statement S or terminate the statement depending on the decision result.

For example when the repeat function is not included in the executed statement the task interpret unit may terminate the statement.

In the meantime when the executed statement does not correspond to the final statement of the robot task TS based on the decision result of the task interpret unit the task interpret unit may read a subsequent statement of the robot task TS S and may determine whether the read statement calls the robot behavior BH S .

In addition when the statement read by the task interpret unit is calling the robot behavior BH the task interpret unit may execute the robot behavior BH associated with the read statement S and may read a decision of the robot behavior BH S .

When the decision calls another robot behavior BH based on a decision reading result the task interpret unit may execute the other robot behavior BH S .

However when at least one activity associated with the decision is defined without calling the other robot behavior BH based on the decision reading result the task interpret unit may execute a corresponding activity S .

For example the decision of the robot behavior BH defined by the user may include a plurality of condition functions that is if function statements and may include a plurality of activities connected thereto.

Accordingly the task interpret unit may execute a corresponding activity by determining a requirement of each if function statement of the read decision.

Accordingly the task execution apparatus may generate a control signal CNT based on the executed activity and may control an operation of the robot for example an operation of the apparatus unit using the control signal CNT.

While this invention has been described in connection with what is presently considered to be practical exemplary embodiments it is to be understood that the invention is not limited to the disclosed embodiments but on the contrary is intended to cover various modifications and equivalent arrangements included within the spirit and scope of the appended claims. Accordingly the actual technical protection scope of the present invention must be determined by the spirit of the appended claims.

