A Multi-Hat Journey to Condition Monitoring and Predictive Maintenance with Amazon Monitron






How I Applied Expertise in Maintenance Management, DevOps, Data Engineering, and Data Science to Implement a Complete Predictive Maintenance Solution with Amazon Monitron and Grafana



![Condition Monitoring Dashboard (Image credit: Author)](https://github.com/chrisdgenius/data-engineering-portfolio/blob/main/assets/profile.jpg)Condition Monitoring Dashboard




Over the past few weeks, I have immersed myself in a journey focused on condition monitoring and predictive maintenance. The experience has been both challenging and extremely rewarding, allowing me to utilize my expertise across various fields. This project has pushed me to apply my specialties in maintenance management, DevOps, data engineering, and data science.


Implementation Amazon Monitron CBM
Maintenance Management: I applied my understanding of what needs to be monitored, the importance of key parameters, and how best to measure them. Focusing on vibration and temperature monitoring, more than 70% of mechanical failures can be detected by tracking changes in these parameters. Vibration monitoring is a broad approach and one of the most accurate, providing extensive data like acceleration in the x, y, and z axes, velocity, crest factor, and temperature, across frequency bands from 0 to 1000 Hz. These parameters are used to detect anomalies in bearings, gearboxes, electric motors, and pumps, identifying failure modes such as lack of lubrication, pump cavitation, misalignment, and excessive wear.


Machine failure
Technology Selection: The next critical step was choosing the right technology for sensors, gateways, cloud storage, and visualization. This is where my expertise as a DevOps engineer became invaluable. After thorough research, I selected Amazon Monitron, an excellent end-to-end system for condition monitoring. It’s seamless, secure, and highly effective, built on AWS IoT, and it integrates easily with other Amazon services. This was a big advantage since one of my top priorities was streaming data and applying statistical models and machine learning algorithms for predictive maintenance.


Amazon Monitron
Data Engineering: After configuring the system, the next step was obtaining live, clean data for further analysis. I configured the live data stream using Kinesis Firehose to stream the data to an S3 bucket. That was just the beginning. Next, I needed to determine the data schema, so I used AWS Glue and a crawler to create a data catalog that I could query with Athena. It was a relief to use SQL for querying my data, but understanding the schema and the parameters’ meaning was essential for performing meaningful analysis. Knowing what analysis to conduct and understanding the implications of every result was crucial.


Technologies for generating insignhts
Data Science: This is my favorite part. I opened Google Colab, connected my Python environment to stream from my S3 bucket, and after setting everything up, I could finally see my data in Jupyter.

Hold on — there was a new client request: “Thanks for the visualization of the vibration and temperature data for our equipment. We’re getting value for our money, but we’d like to project this dashboard across the plant.” I replied, “Fair enough, that’s easy with televisions and projectors.” After setting up the displays, guess what — Oliver asked for more! He wanted a summary dashboard for the operational technology and management teams to have a holistic view of the machine statuses, sensor positions, and other insights.


Vibration readings
Visualization Challenges: Amazon Monitron doesn’t offer this out-of-the-box. So, I put on my DevOps hat again and configured a Grafana dashboard for visualization and alerts. I started with AWS Managed Grafana, but the Athena plugin required an enterprise account and wasn’t free. AWS and Grafana need to make their money, I guess! Not wanting to incur extra costs, I decided to launch an EC2 Linux instance with my favorite Ubuntu OS. I configured AWS CLI, granted the necessary permissions, and tested to make sure my S3 bucket was accessible. Then, I installed Grafana, configured the firewalls, and exposed port 3000. Boom! Grafana was live. I installed the Athena plugin (the reason I left the managed version), connected the data source, and successfully tested the connection.

Next, I donned my data scientist hat once again, this time working with SQL rather than Python. I ran the first query successfully, but when I went back to AWS Glue to run the crawler and refresh my tables, I encountered errors in Grafana due to schema mismatches. It turns out the crawler was changing the schema whenever it ran, causing issues. The solution was simple — ignore null sensor sites to avoid changing the schema.

Final Steps: With clean data ready, I returned to Grafana and began building dashboards. However, I had to ensure I fully understood each parameter, like the “VibrationISO persistentClassificationOutput.” Flattening the data was a crucial step in cleaning it for this project.

Finally, I wore my maintenance and reliability engineer hat, reviewing the meaning and interpretation of each parameter in the payload, testing and confirming their implications, and verifying event types and their respective payload content. Now, with the help of my data scientist hat, I built dashboards combining SQL queries with Grafana charts.


And a shoutout to my buddy, ChatGPT! At first, she was confused, but once I shared the data schema and ensured she understood it, she was able to help me troubleshoot effectively.

The project was a success! Now, the next phase involves exploring various statistical and machine learning models for predictions. Though this is outside the scope of the project, once you find something that encompasses all your expertise, you won’t want to stop.

Feel free to book a call https://calendly.com/okonta-christian/30min and ask me anything about condition monitoring, predictive maintenance, or Amazon Monitron!

Share your thoughts with me in the comment section!
