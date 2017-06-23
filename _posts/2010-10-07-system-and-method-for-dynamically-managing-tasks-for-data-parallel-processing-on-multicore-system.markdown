---

title: System and method for dynamically managing tasks for data parallel processing on multi-core system
abstract: A dynamic task management system and method for data parallel processing on a multi-core system are provided. The dynamic task management system may generate a registration signal for a task to be parallel processed, may generate a dynamic management signal used to dynamically manage at least one task, in response to the generated registration signal, and may control the at least one task to be created or cancelled in at least one core in response to the generated dynamic management signal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08555289&OS=08555289&RS=08555289
owner: Samsung Electronics Co., Ltd.
number: 08555289
owner_city: Suwon-Si
owner_country: KR
publication_date: 20101007
---
This application claims the benefit of Korean Patent Application No. 10 2010 0023194 filed on Mar. 16 2010 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

One or more embodiments of the following description relate to a dynamic task management system and method for data parallel processing on a multi core system that may dynamically manage parallel tasks to fully utilize available cores in order to reduce processing time while maintaining a stable Quality of Service QoS .

Since a conventional single core system using a single processor has problems such as a limitation in increasing a clock speed and power issues a multi core system using multiple processors is being used instead of the conventional single core system.

Changes due to hardware limitations of the conventional single core system inevitably cause changes in software. Since conventional software is based on a single core system advantages such as improvement of performance that can be obtained in a multi core system cannot be expected. This is because the single core structure is completely different that the multi core structure.

Accordingly an important goal in a multi core system is to develop clear software geared towards utilizing the performance and flexibility provided by multi core systems while managing the complexity of a multi core processor program.

Recently to fully exhibit performance of the multi core system research is being actively performed on software for the multi core system such as an Operating System OS for a multi core a parallel programming model enabling parallel processing a dynamic execution environment and the like.

The foregoing and or other aspects are achieved by providing a dynamic task management system including a parallel processing unit to create a registration signal for a task to be parallel processed a load manager to generate a dynamic management signal in response to the generated registration signal the dynamic management signal being used to dynamically manage at least one task and an Operating System OS controller to control the at least one task to be created or cancelled in at least one core in response to the generated dynamic management signal.

The foregoing and or other aspects are achieved by providing a dynamic task management method including generating a registration signal for a task to be parallel processed generating a dynamic management signal in response to the generated registration signal the dynamic management signal being used to dynamically manage at least one task and controlling the at least one task to be created or cancelled in at least one core in response to the generated dynamic management signal.

Additional aspects features and or advantages of example embodiments will be set forth in part in the description which follows and in part will be apparent from the description or may be learned by practice of the disclosure.

Reference will now be made in detail to example embodiments examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. Example embodiments are described below to explain the present disclosure by referring to the figures.

The dynamic task management system of may include a load manager a parallel processing unit and an Operating System OS controller .

The parallel processing unit may generate a registration signal designating a task to be parallel processed.

The load manager may generate a dynamic management signal in response to the generated registration signal. Here the dynamic management signal may be used to dynamically manage at least one task.

The OS controller may control the at least one task to be created or cancelled in at least one core in response to the generated dynamic management signal.

The dynamic task management system may efficiently manage tasks for parallel processing in a dynamic execution environment. For example when several tasks are competitively executed in a core and when another core is in an idle state where no task is executed the dynamic task management system may cancel one or more of the several tasks and may create as many tasks as the number of cancelled tasks in the core in the idle state.

Accordingly the dynamic task management system may dynamically adjust a number of tasks to be parallel processed to improve parallel processing performance or to increase memory utilization.

To efficiently manage tasks for parallel processing in the dynamic execution environment the parallel processing unit may be used as an Application Programming Interface API provided to users to support data parallel processing.

The load manager may measure and manage a load of the system . The OS controller may perform its original function and may also support functions requested by the load manager and the parallel processing unit .

The parallel processing unit may notify the load manager of the existence of data parallel processes which may be expressed by registering . Here registered contents may be separately managed. The load manager may dynamically perform data parallel processing based on information regarding registered data parallel processes and may manage at least one task.

Additionally the load manager may communicate with the OS controller to measure the load of the system or to dynamically manage tasks.

The dynamic task management system may actually be operated along with other modules in response to a command from the load manager .

Thus the dynamic task management system may perform operations for improvement in performance of parallel processing and therefore it is possible to improve performance of the system by measuring and distributing loads of the system .

Referring to when a core becomes available during the dynamic interval the dynamic task management system may duplicate currently processed tasks to create new tasks in the available core .

Specifically when the parallel processing unit generates a registration signal for a task the load manager may generate a dynamic management signal to request generation of the task in the available core .

In response to the generated dynamic management signal the OS controller may create tasks namely DTask and DTask in the available core . Here the tasks may be created by duplicating DTask of currently processed tasks DTask and DTask .

Tasks for data parallel processing that may be created or cancelled by the dynamic task management system may partially process shared data. Accordingly the tasks may execute the same function. In the embodiments multiple data may be processed using a single function in a manner similar to an operation of a Single Instruction Multiple Data SIMD scheme.

Referring to when multiple parallel tasks exist in a single core the dynamic task management system may cancel a part of currently processed tasks may create new tasks and may perform parallel processing using a core that was assigned to the cancelled tasks.

For example when a first task set is assigned to a core in a loading time and when a second task set is to be processed in a run time a part of the core assigned to the first task set may be assigned to the second task set so that the second task set may be processed.

Referring to when a first task set is being parallel processed in cores to as shown in a graph the dynamic task management system may create and process a second task set in cores and as shown in a graph . Here a part of the first task set currently performed in the cores and may be cancelled and a number of new tasks that is identical to the number of cancelled tasks may be created in cores and so that the second task set may be formed.

Referring to the graph a part of the first task set in cores and may be cancelled after time t and the remaining tasks may be processed by the second task set in cores and .

In other words to process the parallel tasks the dynamic task management system may reduce a number of parallel tasks processed in cores and and may allow new parallel tasks to run in cores and as they become available.

Thus it is possible to increase memory availability in view of overall performance and to reduce overhead caused by context switching.

Specifically when a core becomes available in the dynamic interval the dynamic task management system may increase a number of parallel processing tasks and may increase utilization of the core. In other words the dynamic task management system may divide the core and use the divided core based on characteristics of CPU intensive parallel processing tasks rather than unnecessarily generating many tasks. Therefore it is possible to optimize memory usage and reduce an overhead in the dynamic task management system .

The dynamic task management system may differentially adjust a number of cores assigned to parallel blocks and may efficiently manage the parallel blocks. The parallel blocks used herein may have the same concept as a task set.

As shown in each of the parallel blocks may contain at least one task. Here a minimum value and a maximum value of a number of tasks contained in each of the parallel blocks may be set.

Referring to a single data parallel processing block is referred to as a parallel block and may contain information on tasks in each of the parallel blocks. Additionally each of the parallel blocks may maintain the minimum value and the maximum value.

Specifically the minimum value and the maximum value may be maintained to ensure a Quality of Service QoS . This means that only a predetermined number of tasks may be demanded for performance of the parallel blocks not an excessive number of tasks. Since information on the minimum value and the maximum value reflects characteristics of the parallel blocks and the parallel tasks the information may be provided when a user that is well aware of the fact requests parallel processing.

Accordingly the load manager may store a minimum value and a maximum value of a number of tasks created or cancelled in the at least one core and may maintain the stored values.

The OS controller may control the at least one task to be created or cancelled based on the stored minimum value and the stored maximum value.

In other words the load manager may set a range of a number of tasks created or cancelled in each core based on the minimum value and the maximum value.

The minimum value may ensure a minimum performance of each core and the maximum value may secure a saturation point of a performance of each core.

Referring to a minimum value and a maximum value of parallel block may be respectively set to 2 and 4 and a minimum value and a maximum value of parallel block may be respectively set to 1 and 3. Additionally a minimum value and a maximum value of parallel block may be respectively set to 1 and 4.

In other words at least two and up to four tasks may be processed in parallel block . Likewise at least one and up to three tasks may be processed in parallel block and at least one and up to four tasks may be processed in parallel block .

The minimum value and the maximum value of each core may be set based on a priority for a data parallel processing block of each core.

Additionally the load manager may determine a priority for a data parallel processing block of the at least one core. Here the created task may be parallel processed based on the priority.

The dynamic task management system may manage multiple parallel blocks based on the priority of the parallel blocks or based on a minimum value and a maximum value. Since a higher priority parallel block has a higher importance the higher priority parallel block may be processed more rapidly. Additionally a parallel block having a wide range between a minimum value and a maximum value may have as much flexibility as the range and a parallel block with a high minimum value may be requested to be rapidly processed. Thus it is possible to establish policies of multiple parallel blocks based on the above characteristics of parallel blocks.

The dynamic task management system may dynamically manage only parallel tasks or all tasks. Since parallel tasks are CPU intensive tasks parallel tasks may be highly likely to use a single core. Accordingly system performance may be significantly improved based on the parallel tasks only.

However the parallel tasks may not use 100 percent of a CPU due to a standby time caused by synchronization or Direct Memory Access DMA operation.

Therefore the dynamic task management system may dynamically manage tasks more finely based on all of the tasks and loads in the system . Accordingly the load manager may check a load of the at feast one core. When the checked load is equal to or greater than a reference value the load manager may generate a dynamic management signal.

The dynamic task management system may terminate tasks DTask and DTask currently performed in a parallel block and may cancel tasks DTask and DTask. Specifically the dynamic task management system may stably terminate tasks DTask and DTask in a cancellation point. In other words during the termination at least two tasks may be cancelled since a minimum value is set to 2 in the parallel block.

When a termination request for a single parallel block is received the dynamic task management system may check information on tasks. In response to the termination request the dynamic task management system may select at least one of currently executed tasks and may execute a termination command to cancel the at least one selected task.

Specifically the load manager may check at least one task in the data parallel processing block of the at least one core and may generate a dynamic management signal used to request cancellation of the at least one checked task. In response to the generated dynamic management signal the OS controller may control the at least one checked task to be cancelled. For example tasks DTask and DTask may be cancelled under the control of the OS controller .

The OS controller may determine whether a number of tasks remaining in the at least one core is equal to or greater than the minimum value.

When the number of the remaining tasks is determined to be equal to or greater than the minimum value the OS controller may control the at least one checked task to be cancelled.

For example the dynamic task management system may simply select the last task to cancel the selected task.

As another example when multiple tasks exist in a single core the dynamic task management system may select a part of the multiple tasks.

The dynamic task management system may terminate the selected task immediately after the task is selected. Alternatively the dynamic task management system may continue to execute the selected task until a predetermined point in time after the termination request and may terminate the selected task at the predetermined point in time.

When a single parallel block receives a generation request the dynamic task management system may check information on tasks.

Subsequently the dynamic task management system may select at least one task from among the tasks and may generate a dynamic management signal to create a new task. Here the dynamic task management system may duplicate a task placed in the last position so that a new task may be created. Since all tasks in the parallel block are used to process the same operation the above duplication and generation scheme may be applied.

The load manager may generate a dynamic management signal. The dynamic management signal may be used to create at least one new task in the checked data parallel processing block.

In response to the generated dynamic management signal the OS controller may control the at least one checked task to be created.

Additionally the load manager may determine whether a number of tasks in a parallel block is within the range of a minimum value and a maximum value that are set in the parallel block during dynamic management of the tasks.

Specifically when the number of tasks is equal to the minimum value the load manager may ignore the termination request. Likewise when the number of tasks is equal to the maximum value the load manager may ignore the generation request.

The load manager may actually create or terminate tasks and may stop or restart operations of the tasks.

As a result according to one or more embodiments parallel tasks may be dynamically managed to fully utilize an available core and thus it is possible to reduce a processing time while maintaining a stable QoS.

Additionally according to the embodiments it is possible to improve utilization of an available core and to prevent unnecessary generation of tasks in advance by enabling a single parallel task to exist in each core.

Furthermore according to one or more embodiments an equal number of task memories and cores may be used and thus it is possible to prevent a waste of system resources. In addition it is possible to reduce an overhead due to context switching by reducing a number of unnecessary tasks.

In operation a dynamic management signal may be generated in response to the generated registration signal. Here the dynamic management signal may be used to dynamically manage at least one task.

In operation the at least one task may be controlled to be created or cancelled in at least one core in response to the generated dynamic management signal.

In accordance with the dynamic task management method of when a core becomes available utilization of the core may be improved by increasing a number of parallel processing tasks.

For example tasks may be created as necessary and thus a memory may be fully utilized. As another example to process a single core and a single parallel task a number of parallel tasks existing in the core may be reduced and a new parallel task may be operated in the core that becomes available so that system resources may be efficiently used.

Additionally the dynamic task management method of may include checking a load of the at least one core and generating the dynamic management signal when the checked load is equal to or greater than a reference value. Thus it is possible to determine dynamic management based on the load occurring in the system.

To cancel a task at least one task in a data parallel processing block of at least one core may be checked.

For example to cancel the at least one checked task a dynamic management signal may be generated to request a cancellation of the at least one checked task.

In response to the generated dynamic management signal the at least one checked task may be cancelled.

Specifically in operation whether req is greater than 0 may be determined to determine whether a task to be terminated exists. Here req may denote a number of tasks to be terminated.

When the number of tasks to be terminated req is determined to be greater than 0 a victim parallel block may be selected.

In operation the victim parallel block may be set as pb. In operation whether pb has a null value may be determined.

When pb is determined to have a null value the task cancellation operation may be completed by determining that there is no parallel block to be cancelled.

Conversely when pb is determined to have a value other than the null value pb.use may be compared with pb.min in operation . Here pb.use may denote a number of tasks used by pb and pb.min may denote a minimum value of pb. Operation may ensure the overall QoS for the parallel block.

In operation whether data repartitioning is performed may be determined and as a result data may be repartitioned as needed.

In operation when a new value of req is obtained by subtracting 1 from the current value of req the dynamic task management method may return to operation .

Here the victim parallel block may be determined based on the set priority or based on loads in parallel blocks.

Additionally while tasks may be individually terminated in a single parallel block according to the number of tasks to be terminated in the embodiments all tasks able to be terminated in a single parallel block may be terminated. Furthermore the data repartitioning may be performed every time a task is terminated or may be performed once when all tasks are terminated.

Here the number of tasks to be terminated in a parallel block may be equal to a number of tasks to be used in another parallel block. In other words resources of the existing parallel block may be used for a new parallel block.

For example to generate a task in the checked data parallel processing block a dynamic management signal may be generated to request a generation of at least one new task in the checked data parallel processing block.

Specifically in operation whether avail is greater than 0 may be determined to determine whether a task to be created exists. Here avail may denote a number of tasks to be created.

In operation the victim parallel block may be set as pb . In operation whether pb has a null value may be determined.

When pb is determined to have the null value the task generation operation may be completed by determining that there is no parallel block to be generated.

Conversely when pb is determined to have a value other than the null value pb.use may be compared with pb.max in operation . Here pb.use may denote a number of tasks used by pb and pb.max may denote a maximum value of pb . Operation may prevent resources from being wasted due to unnecessary generation of tasks.

In operation whether data repartitioning is performed may be determined and as a result data may be repartitioned as needed.

In operation when a new value of avail is obtained by subtracting 1 from the current value of avail the dynamic task management method may return to operation .

Here the victim parallel block may also be determined based on the set priority or based on loads in parallel blocks.

Additionally while tasks may be individually created in a single parallel block according to the number of tasks to be created in the embodiments all tasks able to be created in a single parallel block may be generated. Furthermore the data repartitioning may be performed every time a task is created or may be performed once when all tasks are created.

Therefore in the dynamic task management method according to the embodiments it is possible to ensure the minimum performance using the minimum value. Additionally it is possible to prevent resources from being unnecessarily assigned based on the uppermost limit that is checked in advance using the maximum value to ensure a QoS of a parallel processing block.

The dynamic task management method according to the above described embodiments may be recorded in non transitory computer readable media including program instructions to implement various operations embodied by a computer. The media may also include alone or in combination with the program instructions data files data structures and the like. The program instructions recorded on the media may be those specially designed and constructed for the purposes of the embodiments or they may be of the kind well known and available to those having skill in the computer software arts. Examples of non transitory computer readable media include magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM disks and DVDs magneto optical media such as floptical disks and hardware devices that are specially configured to store and perform program instructions such as read only memory ROM random access memory RAM flash memory and the like. Examples of program instructions include both machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter. The instructions may be executed on any processor general purpose computer or special purpose computer such as a dynamic task management system or apparatus.

The described hardware devices may be configured to act as one or more software modules in order to perform the operations of the above described example embodiments or vice versa. The software modules may be controlled by any processor or computer. In addition in some embodiments a computer readable storage medium may be distributed among computer systems connected through a network and computer readable codes or program instructions may be stored and executed in a decentralized manner.

As described above according to the embodiments parallel tasks may be managed to fully utilize an available core and thus it is possible to reduce a processing time while maintaining a stable QoS.

Additionally according to the embodiments it is possible to improve a utilization of an available core.

Furthermore according to the embodiments it is possible to enable a single parallel task to exist in each core to prevent in advance tasks from being unnecessarily created. In addition as many task memories as a number of cores may be used and thus it is possible to prevent a waste of system resources.

Moreover according to the embodiments it is possible to reduce an overhead due to context switching by reducing a number of unnecessary tasks.

Although a few embodiments have been shown and described it would be appreciated by those skilled in the art that changes may be made in these embodiments without departing from the principles and spirit of the disclosure the scope of which is defined in the claims and their equivalents.

