
Can be done through APKtool

apktool -d application.apk -r(to exclude resources)

But with apk tool we would need to convert the smali code to java using dex2jar

--------

Important files to look at 

strings.xml (Check for creds, API keys, URLS, firebase)
AndroidManifest.xml

---------

**Cloud Enum Link**: [https://github.com/initstring/cloud_enum](https://github.com/initstring/cloud_enum)

**AWS CLI:** sudo apt-get install awscli

**AWS CLI Documentation:** [https://aws.amazon.com/cli/](https://aws.amazon.com/cli/)

cloudenum.py -k appName
Will identify s3 buckets

aws configure --profile appName
Now you set it up with the access and secret key 

aws s3 ls s3://appName --profile appName
Will enumerate the S3 bucket

-----------

If exported = true is allowed for an activity then that activity can be directly accessed

Through adb shell

am start com.applicationName/.ExportedActivity

----------

Firebase Enum

**Firebase Enum Github:** [https://github.com/Sambal0x/firebaseEnum](https://github.com/Sambal0x/firebaseEnum)

-k to enumerate a company

It is possible that certain areas of the firebase url are protected and some are not. It could be interesting to enumerate them to find something interesting

-------------

