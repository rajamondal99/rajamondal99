1. To see cron run time goto this website
``` https://crontab.guru/ ```

2. To get live stock market data refer to this website(for any language)
```https://kite.trade/```

3. To run cron job or sheduler in node js use this package
```
npm install node-cron

nodecron.schedule("0 0 */1 * *", async function () {
    var date_time = new Date();
    logger.info(`[${date_time}] -- cron started -- createContestCron`);
    try {
      /**
       * 0 = sunday
       * 6 = saturday
       */
      if (![6, 0].includes(date_time.getDay())) {
        var curr = new Date();
        var lastday = new Date(
          curr.setDate(curr.getDate() - curr.getDay() + 6)
        );
        var nextWeekSameDayDate = new Date(
          lastday.setDate(lastday.getDate() + curr.getDay() + 1)
        );

        const contests = await contestModel.find({});
        if (contests.length > 0) {
          contests.forEach(async (element) => {
            var enroll = await contestEnrollModel.create({
              contest_date: nextWeekSameDayDate,
              contest_id: element._id,
              contest_name: element.name,
              contest_category_id: element.category,
              players: [],
            });
            if (enroll && enroll._id != null) {
              console.log(`created enroll ${enroll.contest_name}`);
            } else {
              console.log(`faild to created enroll`);
            }
          });
        }
      }
    } catch (error) {
      logger.error(`[${date_time}] -- cron failed -- createContestCron`);
    } finally {
      logger.info(`[${date_time}] -- cron end -- createContestCron`);
    }
  });


```

4. To use soft delete in nodejs and mongodb read this blog
    ```
    https://nour-karoui.medium.com/implementing-soft-delete-in-mongodb-with-mongoose-405c008d0e29
    ```
    
5. How to install NodeJs on server

      i> download nodejs from Nodesource.
    ```
    curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
    ```
    ii> install nodejs
    ```
    sudo apt-get install -y nodejs
    ```
    iii>Check the installation 
    ```
    node --version && npm --version
    ```

6. How to use pm2 as a process manager
    i>Install pm2 using the commands below
    ```
    sudo npm i pm2 -g
    ```
    ii>Start the application using the following command
    ```
    pm2 start app.js
    ```
    
7. How to use serve packege to deploy react build on server
    i> install serve globally
    ```
    npm install -g serve

    ```
    ii> now serve your build folder
    ```
    serve -s build
    ```
 

