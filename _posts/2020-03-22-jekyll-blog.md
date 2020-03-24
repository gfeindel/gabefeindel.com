---
title: "How to host a blog with Jekyll and Amazon S3"
categories: blog jekyll aws s3
comments: false
layout: post
---
A couple years ago, I decided to start a blog. My purpose for the blog is to create an online presence, practice writing, and give back to the IT community. I'm a minimalist and a coder, so a static website intrigued me. I stumbled across a few blog posts about using Jekyll with S3, so here I am. This post explains how I setup my Jekyll blog usin Amazon S3.


## Dev system setup

I since I work primarily on Windows at work, my primary system is Windows. Rather than fight with Jekyll on Windows, I created a Hyper-V virtual machine using the Ubuntu 18.04 LTS template. I write my posts in Windows, but build and push to my website using the Ubuntu VM. In the future, I might use an Amazon Lightsail instance to both build and host my site, like [Andy Grove did](https://andygrove.io/2018/05/hosting-jekyll-lightsail-lets-encrypt-ssl/).

### Build Ubuntu 18.04 LTS Hyper-V VM
- Create using Quick Create wizard
- Enable guest services

### Install and configure Jekyll and AWS CLI

- API keys stored in environment variables. DON'T commit these in your git repository! I did by accident and got a nasty-gram from Amazon. Apparently they have a bot that scans Github for such foolishness. Thanks for watching my back, Amazon!
- Follow Jekyll install instructions [here](https://jekyllrb.com/docs/installation/ubuntu/)
- `sudo gem update --system`
- Install git `sudo apt install git`
- Clone the repo. Inside the repo folder, run `bundle install` to add missing gems from Gemfile.
- `sudo apt install awscli`
- `aws configure` and provide needed information.
- To deploy updates to your bucket, build Jekyll and run `aws s3 sync _site/ s3://<bucketname>`

## Amazon S3

I created an S3 bucket, configured it as a website, used Route 53 for DNS and CloudFront for caching. I used Route 53 and CloudFront, so I could host my website at the root domain, gabefeindel.com. Without them, S3 must use a subdomain, like www.gabefeindel.com. 

