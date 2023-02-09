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