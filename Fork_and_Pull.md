---------------- FORK & PULL WORKFLOW ----------------

The way the Fork & Pull works is that anyone can Fork a repository and make changes locally. They don't have the ability to push their potentially damaging code. They can however request that the host repository pull their changes if they would like using a Pull Request. ( This is a very common workflow in the open source community )

42. Find a repository you'd like to work on and click Fork in GitHub

43 - 45. git clone https://github.com/derekbanas/CrazyTipCalc.git
   # Get the URL for the fork on GitHub and clone it on your local computer

46. git remote add upstream https://github.com/derekbanas/CrazyTipCalc.git
    # Assigns the original remote and not the fork to the keyword upstream
    
47. git fetch upstream
    # Pull in changes made in the original repository with effecting the local files

48 - 53. I can change a file locally, stage and commit it. I can then push it to more Fork on GitHub.

54. git merge upstream/master # Merges files on GitHub with my local files

55. If I think my changes should be merged with the original repository I can make a Pull Request. Click on Compare, review, create a pull request on GitHub.

56. Changes are listed as well as other data associated with your Forked version. Click the button labeled Create Pull Request if you think you're ready.

57 - 58. Leave a detailed reason why the Pull Request should be excepted and click Send Pull Request

59. The owner of the original repository can see how many Pull Requests they have received on the right side of the screen.

60 - 63. They can go through the Pull Requests and decide what to do.  

64 - 65. To merge click Merge Pull Request in GitHub and then leave a detailed explanation why it was done.
