# Laboratorio - Analisis Estatico

**Nombres:** Juanita, Julia, Sebastian, Wilson


## Exercise 1: Embracing Continuous Delivery with Azure DevOps
### Task 1: Set up a pipeline that integrates with SonarCloud

1. In your new Azure DevOps project, go to Pipelines under the Pipelines tab, then click on Create Pipeline:
2. Choose one of the options (YAML OR CLASSIC):

### YAML Editor

1. We will not be using this feature today. In our case we want to analyze code in the git repo that we imported earlier, right in the same account as this pipeline. So, we select Azure Repos Git:
   ![image](https://user-images.githubusercontent.com/62759668/202875940-a0b3ca03-63e3-4b64-a9a5-b90ae6e5e74e.png)

2. On the next screen select the git repository that you imported earlier, SonarExamples:
   ![image](https://user-images.githubusercontent.com/62759668/202875948-f51c61dc-eb47-4eec-b4de-94063e9f0575.png)

3. Now select a YAML file template. We will be building and analyzing the .NET code in our example imported repository, so we will start by choosing the .NET Desktop YAML template:
   ![image](https://user-images.githubusercontent.com/62759668/202876003-cfdc0b49-d272-426c-8ba6-56d329d04976.png)
   
4. The YAML editor will open with the template YAML file. In order to configure it correctly you will need to adjust it (or replace it) so that it looks like the following example file:
   ```
   net-desktop-sonarcloud.yml
   ```
   we need to customize it to our needs:
   1. Modify the Build task, change the pointer to the solution **(add wildcards as our solution is not located in the root of the repo):
      ![image](https://user-images.githubusercontent.com/62759668/202876114-635b2139-4349-4c8a-b4a4-8ee0254df695.png)
   2. Modify the Prepare Sonarcloud task with your own information. Follow the information in Sonarcloud previous windows to:
      
      1. Setup a service connection
      2. Modify the task with the values provided on the Sonarcloud window guide. Use your service endpoint created and organization/project name and key values, not the default ones!! click Add after modifying those values.
         ![image](https://user-images.githubusercontent.com/62759668/202876465-ce69e86b-9d1f-4935-b92b-6c602440de3a.png) /
         When you are done making the changes to the file, click Save and Run:
         ![image](https://user-images.githubusercontent.com/62759668/202876514-3c32dee1-495a-4157-94da-4a31400f2882.png)

