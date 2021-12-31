

# Assignment-1 AWS code submit



Problem Statement: 

- Create a AWS Account and create a Code Commit Repository inside the AWS Account.

- Install Git in the local machine and create two random HTML files inside a particular folder

- Configure git with the remote Code commit repository and push the folder





![image-20211231172812692](https://s2.loli.net/2021/12/31/WxC7agzYJPjBLZ8.png)



```bash
git push -u origin master
```

![image-20211231183253318](https://s2.loli.net/2021/12/31/adV8WGTsIDux4bi.png)







# Assignment-2 AWS code build

`buildspec.yml`

```yaml
version: 0.2

phases:
  install:
    runtime-versions:
      nodejs: 10
    commands:
      - echo "installing nodejs"
    
  pre_build:
    commands:
      - echo "we are in the pre-build block"
    
  build:
    commands:
      - echo "we are in the build block"
      - echo "we will run some tests"
      - grep -Fq "xiaomei" index.html
    
  post_build:
    commands:
      - echo "we are in the post build phase"

artifacts:
  files:
    - "index.html"
  name: webpage
```



`index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <title> The test of AWS CodeBuild </title>
</head>
<body>
    <div align='center'>
    <h1> "TA xiaomei" </h1>
    <h2> This application was deployed using AWS CodeDeploy </h2>
    </div>
</body>
</html>
```







![image-20211231191922601](https://s2.loli.net/2021/12/31/KQCIA2vkxhmDsNG.png)



# Assignment-3 AWS CodeDeploy



![image-20211231195856858](https://s2.loli.net/2021/12/31/VlaW4iuydFRmKBN.png)

pending for code deploy 



# Assignment-4 AWS CodePipeline

![image-20211231200249500](https://s2.loli.net/2021/12/31/adgmFTB3scYiIr6.png)



![image-20211231200403375](https://s2.loli.net/2021/12/31/rcM18lVdunkoiBm.png)

