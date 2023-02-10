VOLUMES
    kubernetes volumes are more stronger and flexible as compared to docker volumes
    The core functionality is same, but the control over their implementation is greater in kubernetes

    In kubernetes, if container is crashed and restarted, the existing data is lost if no volumes are used.

    Types of drivers:
    1. emptyDir : emptyDir driver is a Pod specific volume driver.
            All the containers in that Pod can access this volume.
            Hence, it solves the issue of data persistency for crashes and restarts.
            But what if we have replicas of a Pod ?
            This will not work. If 1st Pod crashed, and 2nd is served, as emptyDir is Pod specific, it will be two separate volumes.
            Hence, data inconsistency.

    2. hostPath : hostPath is Worker Node specific volume driver.
            This is kind of like Bind Mounts.
            All the Pods on Worker Node (running on same machine) can access this volume.
            This won't work if Worker Node is distributed over multiple machines. Its great for working with single node environment.
            
PERSISTENT VOLUMES
    Node and Pod independent volume.

