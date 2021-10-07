---
title: Features
onpagelink: features
weight: 2

---

### **Features**

Following are the key features of Zulip

- MARKDOWN OPTIMIZED FOR CHAT: Express your ideas clearly with bulleted lists, bold, italics, and much more.
- EMOJI AND EMOJI REACTIONS: Have fun expressing yourself with emoji!
- INLINE IMAGE, VIDEO, AND TWEET PREVIEWS: Zulip automatically generate a previews of links you send in conversations
- DRAG-AND-DROP FILE UPLOADS: Drag a file into the compose box and start sharing and discussing work with team mates has never been easier.
- CODE AND QUOTE BLOCKS: Discuss code with ease using Markdown code blocks (and syntax highlighting). And discuss blocks of text with ease with block quotes.
- CUSTOMIZABLE AUTOMATIC LINKIFICATION: Customize Zulip’s markup to automatically link back to your issue tracker or GitHub when you type “#1235” or a commit ID.
- INTEGRATIONS: Get alerts and updates from your favorite services with off-the-shelf integrations for Trac, Nagios, GitHub, Jenkins, and more.
- API: Zulip has a dead-simple RESTful API and Python bindings
- MOBILE APPS: Supports native quality iOS and Android apps.
- DESKTOP APPS: Supports Multi Platform Desktop Apps.
- ENTERPRISE-GRADE SECURITY: Zulip is used by some of the most security-conscious organizations in the world.
- FULL-TEXT FULL-HISTORY SEARCH: Search is both snappy and smart, helping you look for text, people, and threads of conversation, with advanced search operators for fine-grained control.
- HISTORY: Join a stream and see its history, so even new team members are never out of the loop.
- STARRED MESSAGES: Keep a todo list of messages to come back to, or keep track of interesting conversations.
- STATISTICS: Zulip has a powerful set of analytics available to help you see how your organization communicates.
- ONE-ON-ONE AND GROUP PRIVATE CONVERSATIONS: Lightweight private conversations with one or as many people as you need.
- TEAM AVAILABILITY: See who is currently online at a glance.
- PRIVATE STREAMS: Enjoy the benefits of threaded conversations while controlling your audience and privacy.
- MESSAGE EDITING: Don’t worry, you can always fix that typo, either in the body of message or its topic.
- CONVERSATIONS THREADED BY TOPIC: Participate in several conversations with the same group at once, without getting lost or overwhelmed.
- CATCH UP IN NO TIME: With topics, hotkeys and snappy performance, usefully reviewing hundreds of messages takes just minutes.
- FULLY INTERNATIONALIZED: The Zulip UI is fully internationalized and has been translated into over a dozen languages.
- CUSTOMIZABLE LOGIN AND REGISTRATION: Customize the available authentication methods and customize the login and registration pages for your organization using Markdown.
- VIDEO CALLS: Create and join video calls with a single click. Powered by your choice of Zoom, Jitsi Meet or Big Blue Button.
- FLEXIBLE AUTHENTICATION: Supported authentication providers include LDAP, SAML, Google, GitHub, GitLab, Apple, and more.
- DATA IMPORT: Import an existing Slack, Mattermost, HipChat, Stride, or Gitter workspace into Zulip.
- CUSTOM PROFILE FIELDS: Use Zulip to store directory information, links to social media profiles, food preferences, or anything else.
- GUESTS: Guests cannot see or join streams unless they are explicitly added. Perfect for partners, vendors, and temporary contractors.
- CUSTOM BRANDING: Use your logo instead of Zulip’s in the desktop and webapp.
- INTEGRATE WITH IRC, MATRIX, OR SLACK: Two way integrations with IRC and Matrix, and one way integration with Slack.
- MODERATION: A full suite of tools for moderating open communities.
- DATA EXPORTS: No vendor lock-in. Export your hosted Zulip to an on-premises installation at any time.
- YOUR FEATURE HERE: Zulip is open source, so if something important for your use case is missing, you can make it happen!
 
### Installation Instructions

####  

#### Linux Server

- **Step1: Download the latest release**  
   ```
  
  cd $(mktemp -d)
  wget https://www.zulip.org/dist/releases/zulip-server-latest.tar.gz
  tar -xf zulip-server-latest.tar.gz
  
  ```
- **Step 2: Install Zulip**  
   ```
  
  sudo -s  # If not already root
  ./zulip-server-*/scripts/setup/install --certbot \
      --email=YOUR_EMAIL --hostname=YOUR_HOSTNAME
  
  ```
- **Step 3: Create a Zulip organization, and log in**
- **Step 4: Configure and use**
 
