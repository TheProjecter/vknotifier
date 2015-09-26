It solves the problem of limited api queries frequency in vk.com. It takes tasks of user notifications, makes a queue from them and work that queue considering requests frequency limit.

For start working, you have to change application id and secret key in NotifyQueue.class.php and set delay between queries in worker.php. After that add worker.php on cron shedule (crontab example is included).

To add some task to queue use NotifyQueue::addTask($ids, $message); where $ids is comma-separated list of user ids, and $message is notify text that should be in utf-8. Number of ids may be over 100, class will divide it automatically.