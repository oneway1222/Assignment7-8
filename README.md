# Project 7 - WordPress Pentesting

Time spent: **8** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.2.5
  - [x] GIF Walkthrough:<img src='http://i.imgur.com/2tlNfkv.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' /> 
  - [X] Steps to recreate: 
     - Create new text post (this does not work in comments)
     - Splice HTML tag with shortcode tag to sneak in alert
  - [X] Affected source code:
    - [Link](https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8)
    
2. (Required)Authenticated Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2  
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: <img src='http://i.imgur.com/dLSUl4q.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' />
  - [X] Steps to recreate: 
   - Create new text post
   - Insert a url like https://youtube[.]com/watch?v=abc with "< s v g on load=alert(1)>" concatenated at the end, which will escape WordPress's autoembed function and return untouched
   - When the post is viewed, the alert will show  
  - [X] Affected source code:
    - [Link](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
    
3. (Required) Authenticated Cross-Site Scripting (XSS)
  - [X] Summary: 
    - Vulnerability types:XSS
    - Tested in version:4.2.2   
    - Fixed in version: 4.2.5
  - [x] GIF Walkthrough: <img src='http://i.imgur.com/F1TGfxJ.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' /> 
  - [x] Steps to recreate:
       - Login as an administrator
       - Create new text post
       - Add alert script to the end of a link
       - Alert will appear whenever page is viewed 
  - [X] Affected source code:
    - [Link](https://core.trac.wordpress.org/changeset/36185)
    
4. (Optional)Open Redirect
  - [x] Summary: 
    - Vulnerability types:HTTPS Redirect
    - Tested in version:4.2.4
    - Fixed in version: 4.2.7
  - [x] GIF Walkthrough: <img src='http://i.imgur.com/SXhWdKC.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' />
  - [x] Steps to recreate: 
    - Create a URL that takes an encoded redirect link and concatenates it to the end of WordPress login page
     - While logged out, go to the "login" page that you just created
     - When you click sign in, the link will redirect the page you added to the link
     - A hacker could use this spoof a login page and trick a user into giving them their credentials 
  - [x] Affected source code:
    - [Link](https://core.trac.wordpress.org/changeset/36444)
    
5. (Optional) Authenticated Cross-Site Scripting (XSS) via Media File Metadata
  - [x] Summary: 
    - Vulnerability types:XSS
    - Tested in version:4.2.4
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: <img src='http://i.imgur.com/meAnTdw.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' /> 
  - [x] Steps to recreate: 
   - Upload an mp3 file to the WordPress media library, under editor or administrator
   - Insert an audio playlist containing this mp3 into a post
  - [x] Affected source code:
    - [Link](https://github.com/WordPress/WordPress/commit/28f838ca3ee205b6f39cd2bf23eb4e5f52796bd7) 
    
## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2019] [Hangill Chong]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
