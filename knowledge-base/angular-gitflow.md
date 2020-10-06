---
id: angular-gitflow
title: Publish an Angular project
sidebar_label: How to publish an Angular project
---

### Steps : 
1. Go to ***development*** branch and get latest changes.
   *  run ```git checkout development ``` then ```git pull``` 

2. Change to the ***branch*** you want to merge to ***development***.
   * ```git checkout <branchName>``` 

3. Merge ***development*** -> ***yourBranch***.
    * ``` git merge development ```

4. Check everything is going well.
    * Always check crucial files (e.g AppModule, Enviroment etc)
  
5. Change to ***development*** branch and merge
    * ``` git merge <branchName> ```
  
6. Delete branches that we don't want any more

7. Merge ***development*** to ***master*** 
   * ``` git checkout master ```    
   * ``` git merge development ``` 

8. Now we create a [Git tag](https://www.atlassian.com/git/tutorials/inspecting-a-repository/git-tag) 
    * Follow [Semantic Versioning](https://semver.org/) for your tag   

9. After create our tag we can now **push** to our repository  
   * ``` git push origin <version tag> ```

10. Build application and check that everything is ok. 
   * Run ```ng build``` to build the project. Use the ```--prod``` flag for a production build. Use ng build ```--configuration=staging``` to build artifacts for staging environment.

11. The build artifacts will be stored in the dist/ directory.