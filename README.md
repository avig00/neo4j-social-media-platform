# DS5760 NoSQL for Modern Data Science Applications:
# Mini Project 3 – Designing a DSI Social Network Database in Neo4j

## About
The goal of this project is to create a graph database using Python and Neo4j that stores information about users, posts, and the connections between them for a social media platform for Data Science Institute students and alumni.

## Requirements
This project requires the following:
* Docker
* Python
* Neo4j

## Database Design
This graph database consists of 5 types of nodes and 7 types of edges. 

The types of nodes and their properties are listed below. 

1. Users - This node stores information about students that are currently attending or have graduated from the DSI. The attributes of this node are as follows:
    * VUnetID (unique identifier for each user)
    * Name
    * Graduating class (Class of [year])
    * Password
    * Email
    * Fields of interest (Project-based and career-oriented interests)
    * Undergraduate major
    * General interests (Interests outside of projects and career, hobbies, etc.)

2. Posts - This node stores information about posts that users have created. The attributes of this node are as follows:
    * Key words
    * Text (Full post)
    * Created by [user]
    * Reacted by [user(s)]
    * Timestamp

3. Events - This node stores information about DSI events. The attributes of this node are as follows:
   * Name
   * Description
   * Date
   * Time
   * Hosted by (List of users that are hosting the event)
   * Attendees (List of users that are attending the event)

4. Comments - This node stores information about comments that users have created to reply to posts. The attributes of this node are as follows:
   * Created by [user]
   * Reacted by [user(s)]
   * Text
   * Timestamp

5. Reactions - This node stores information about user reactions to posts and comments. The attributes of this node are the reaction types, of which there are four:
   * Happy
   * Sad
   * Angry 
   * Scared

The types of edges and their properties are listed below. 

1. IS_FRIEND_OF: This edge connects users to other users. For this edge, the Users node is both the source and the destination node.

2. HOSTED_BY: This edge connects events to the users that are hosting the event. For this edge, the Events node is the source node and the Users node is the destination node.

3. ATTENDED_BY: This edge connects events to the users that are attending the event. For this edge, the Events node is the source node and the Users node is the destination node.

4. RELATED_COMMENTS: This edge connects a post to comments that users have created in response to the post. For this edge, the Posts node is the source node and the Comments node is the destination node.

5. CREATED_BY: This edge connects two pairs of nodes:
   * Pair 1: This edge connects a post to the user that created it. Thus, the Post node is the source node and the Users node is the destination node.
   * Pair 2: This edge connects a comment to the user that created it. Thus, the Comments node is the source node and the Users node is the destination node.

6. REACTED_BY: This edge connects two pairs of nodes:
   * Pair 1: This edge connects a post to a user that has reacted to it. For this edge, the Posts node is the source node and the Users node is the destination node.
   * Pair 2: This edge connects a comment to a user that has reacted to it. For this edge, the Comments node is the source node and the Users node is the destination node.

7. REACTION_TYPE: This edge connects a user that has reacted to a post or comment to their reaction type. For this edge, the Users node is the source node and the Reactions node is the destination node.

## Potential Benefits and Challenges of the Platform
This platform could have several potential benefits for DSI students and alumni. Some examples are listed below:

* Creating a sense of community: A centralized platform that specifically caters to past and present DSI students could help to foster a sense of community, allowing people with shared professional and general interests to connect both inside and outside the classroom.
* Enhanced networking possibilities: By connecting current students with alumni, the platform could enable mentorship and networking opportunites for current students. This could be highly beneficial, potentially helping students secure internships and jobs.
* Centralized event management: The platform could serve as a central hub for the planning, organization, and promotion of DSI events. By allowing students and alumni to interact casually outside of the classroom, this could help to further strengthen a sense of community between past and present DSI students.

In spite of the benefits listed above, there are also some potential challenges with using this platform. Some examples are listed below:

* Privacy and security measures: Presently, the platform lacks the security measures necessary to protect the personal data of users. For this platform to be truly viable, it is imperative that such security measures are implemented to prevent the theft and/or distribution of sensitive user data.
* Scalability: As more students join and graduate from the program, the platform will need to scale effectively to avoid performance issues. However, this will require a robust architecture, and the current architecture may not be sophisticated enough to support this level of growth. 
* Content moderation: Presently, the platform lacks the required content moderation measures to ensure that the platform remains a fun but professional and respectful place for past and present DSI students to connect. Conent moderation measures are also needed to prevent the spread of misinformation. 





