# JobUI
* __Customizable and Infinite Jobs are supported now. you can change or add jobs in `plugin_data\JobUI\plugin.yml`.__
* __Customizable message will be added soon.__
* I changed the default permissions to "op" to prevent earning money in a "Build and Mine Protected World" like Lobby.
* You will learn how to let players use /job command and earn money only in a specified world, but before you need to install the PurePerms plugin.
### Default Jobs
* Tree-Cutter: By joining this job, when you break any kind of logs with any directions you will earn 25$.
* Miner: By joining this job, when you break Stone 25$, Coal ore 30$ and Iron ore 35$.
### Dependencies:
* [FormAPI by jojoe77777](https://poggit.pmmp.io/p/FormAPI/) [[Download]](https://poggit.pmmp.io/r/41263/FormAPI.phar) [[GitHub]](https://github.com/jojoe77777/FormAPI) __(Required)__
* [EconomyAPI by onebone](https://poggit.pmmp.io/p/EconomyAPI/) [[Download]](https://poggit.pmmp.io/r/34531/EconomyAPI.phar) [[GitHub]](https://github.com/poggit-orphanage/EconomyS/) __(Required)__
* [PurePerms by 64FF00](https://poggit.pmmp.io/p/PurePerms/) [[Download]](https://poggit.pmmp.io/r/70018/PurePerms.phar) [[GitHub]](https://github.com/poggit-orphanage/PurePerms) (Optional)
### How to let players use /job command and earn money only in a specified world?
* As I said you need to install the PurePerms plugin.
* __*Before completing the next steps, make sure that `enable-multiworld-perms` has been set to `true` in `plugin_data\PurePerms\config.yml`.*__
* Open this file path `plugin_data\PurePerms\groups.yml`. Then the only thing that you should do is to add the world and permissions to the Group you want. I will give an example below:
```yaml
---
Guest:
  alias: gst
  isDefault: true
  inheritance: []
  permissions:
  - jobui.command.retire
  worlds:
    Mine:
      isDefault: false
      permissions:
      - jobui.command.job
      - jobui.earn.break
      - jobui.earn.place
...
```
* If a player is in the Guest group, he won't be able to use /job command in every world except the "Mine"
* Also, he won't be able to earn money by having a job in every world except the "Mine" but he can use /retire in every world.
### Image
![Preview](https://www.mediafire.com/convkey/7ca9/muxd8cv9quuoo6vzg.jpg)
### To-Do list
* [X] Adding Customizable feature for jobs, so that you will be able to add more jobs
* [ ] Adding Customizable feature for texts of the UI and every messages (in 3 days or less)
* [ ] Using the FormAPI library instead of FormAPI plugin (not in 3 days)
### Permissions and Commands:
Permission | Command | Default | About
---------- | ------- | ------- | -----
jobui.command.job | /job | op | Able to see the UI of the Jobs
jobui.command.retire | /retire | true | Able to be retired 
jobui.earn.break | - | op | Able to earn money of a breaking Job
jobui.earn.place | - | op | Able to earn money of a placing Job
* As you see, there is an independent /retire command. Although there is a button to get retired through the Form, I've added /retire command to let players get retired when they don't have permission to use /job.
