# utl-repairing-the-calssic-l980s-display-manager-editor
Repairing the Calssic l980s display manager editor

    Repairing the Calssic l980s display manager editor

    github
    https://communities.sas.com/t5/New-SAS-User/Command-line-disappears/m-p/528224

    SAS Forum:

    Glad to see users of the Calssic 1980's display manager editor.

    SOAPBOX ON

    There is very limited support to fix installed bugs and reinstalling
    legacy functionality into the originally solid classic editor.

    I find I have to repair profile.sas7bcat periodically, I also back it
    up about once a month. Probably because of all that bloated EG stuff in the profile.
    I wish there was an option to uninstall EG?

    SOAPBOX OFF

    POSSIBLE FIX

       1. Rename the current profile.sas7bdat to profbak.sas7bdat.
          It is located at '%put %sysfunc(pathname(sasuser));'
          Mine is located in 'c:\etc'

       2. Open up SAS (I think it defauls to EG?)
          Type and run this  program.
          proc datasets lib=sasuser mt=cat;
             repair profbak;
          run;quit;

          NOTE: Repairing SASUSER.PROFBAK (memtype=CATALOG).

       3. Rename profbak.sas7bdat to profile.sas7bdat

