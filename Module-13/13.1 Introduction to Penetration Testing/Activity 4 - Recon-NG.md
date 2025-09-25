## Activity Objectives:

By the end of this activity, students will be able to effectively utilize Recon-ng to gather and analyze open-source intelligence (OSINT) on a given target. They will learn how to configure Recon-ng, use various reconnaissance modules, set API keys, run OSINT queries, and generate reports summarizing the information collected. The students will develop skills in passive reconnaissance techniques, enabling them to gather information without directly interacting with the target systems.

## Activity Instructions:

Students will use recon-ng to find publicly available information that could be useful in an OSINT investigation. 
1. Ensure that you have recon-ng installed on your Kali or Parrot VM. If not run `apt update && apt install -y recon-ng`. (You will have to reboot your VM after installation.)
2. Search the marketplace for the recon modules you will be using within this activity using `marketplace search recon`.
3. Get information about the hackertarget module using `marketplace info hackertarget`.
4. If you had to install recon-ng, you have "no modules enabled/installed", or the hackertarget is not installed, run `marketplace install hackertarget` to install the module to recon-ng.
5. Start by creating a new workspace to organize your project `workspaces create <workspace_name>`.
6. List the modules available to you (i.e installed locally) using `modules search`.
7. Load the module using `modules load <module_name>`.
8. View the options you can set for the module using `options list`.
9. Set a website or URL you have permission to scan as your target using `options set SOURCE <target_domain>`.
10. Run the hacker_target module, using `run`.
11. Print the contents of the workspace hosts table i.e. every host the workspace has collected by executing `show hosts`.
12. Create a csv report by installing, loading, and/or running the "reporting/csv" module.

