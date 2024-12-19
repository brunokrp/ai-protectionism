# **Artificial Intelligence Protectionism** <br/> **Distribution and prevalence across the world**
By leveraging natural language processing tools, this project aims to understand the prevalence and distribution of nationalistic policies throughout the world. Using data from the Digital Policy Alert, it 


## **1: Artificial intelligence and economic nationalism**
There has been a perceptible uptick in global interest in two different, but complementary, topics: artificial intelligence (AI) and economic nationalism. AI has been, during the past few years, one of the most discussed technologies in the world. From the 2010’s novel applications of deep and reinforcement learning to the recent innovation brought forth by large language models (GPT and other transformer architectures), the world’s eyes are paying close attention to the development of this technology. Not only are markets deploying valuable resources to develop and adopt it, but governments have also taken considerable efforts to regulate and foster the artificial intelligence environment - semiconductors, data infrastructure, machine learning models, and its applications - foreseeing the potential risks and gains of such a ubiquitous technology. 

At the same time, the world has also seen the rise of economic nationalism and how it reshapes global trade dynamics. Economic nationalism is marked by policies prioritizing domestic industries over international cooperation, such as Trump's intentions to impose widespread tariffs on imports, or the CHIPS Act, which subsidizes the U.S. semiconductor industry. These policies challenge decades of efforts to promote liberal trade. Simultaneously, international organizations like the World Trade Organization (WTO) have faced criticism for their inability to adapt to new economic realities or mediate disputes effectively. This failure has undermined trust in multilateral trade frameworks, prompting nations to pursue unilateral strategies that reflect growing skepticism toward globalization and free trade principles.

Both topics are now converging under the umbrella of the New Techno-nationalist movement. For this movement, the nation and its technologies must be defended through “protectionism measures, domestically supported manufacturing and technology, the rejection of multilateralism, the deployment of zero-sum narratives, and in some circumstances, ethnic discrimination”[1]. Such an argument contrasts with the liberal notions of free trade, international cooperation, and multiculturalism that made up much of the economic arguments of the last decades. Even more so when nationalistic arguments come from countries that were the winners of the free world - the US and Western Europe. 

Thus, the convergence of artificial intelligence (AI) and economic nationalism represents a pivotal issue in public policy due to its transformative implications for global governance, trade, and technology. AI's rapid advancements demand coordinated regulation and investment to address ethical concerns, workforce displacement, and geopolitical competition. Simultaneously, the rise of economic nationalism challenges established trade norms, fostering protectionism and disrupting global supply chains. 

### **Research Questions**
This project's objective is to map the distribution of techno-nationalist AI policies across the world, identifying its main proponents. As such, the following are the research questions it aims to answer:

1. Which terms are more present in AI policies?
2. How are terms related to protectionist policies distributed among different regions? 
3. Which regions have the highest percentage of protectionist policies?

### **Significance and importance to public policy**
Answering these questions is essential for understanding how governments approach AI development and regulation, revealing global priorities and strategies. Analyzing the most common terms in policies can be effective in highlighting the foci of government action: whether it is innovation, regulation, or national security. The distribution of protectionist language across regions also shows how domestic interests are emphasized over international cooperation. Besides, identifying regions with the highest levels of protectionist measures uncovers patterns in economic strategies, shedding light on potential trade disputes and collaborations. These insights are vital for crafting policies that balance technological advancement, domestic priorities, and the need for global collaboration.

## **2) Methods**
### **2.1) Data sources**
#### **2.1.1) Global Trade Alert (GTA)**
The Global Trade Alert is a database that organizes information regarding governmental changes to market conditions. It first started in 2008 and has since then managed to store more than 70,000 governmental interventions. This reaction paper was based on this dataset because of the detailed taxonomy used to structure data about government interventions. One of its key is the categorization of each intervention according to the direction of the induced change: liberalizing or harmful toward foreign interests. 

GTA categorizes each intervention in one of three colors: 
🔴 Red - when the intervention almost certainly discriminates against foreign commercial interests;
🟠 Amber - when the intervention likely involves discrimination against foreign commercial interests;
🟢 Green - when the intervention liberalizes on a non-discriminatory (i.e., most favored nation) basis, or improves the transparency of a relevant policy.

#### **2.1.2) Digital Policy Alert (DPA)**
The Digital Policy Alert is a database that monitors digital policy developments worldwide. Developed by the same group that created the GTA database, it structures the information collected along two primary groups: i) Information on the acting regulatory authority and ii) Information on the substance of the regulatory change. Besides, the DPA database monitors a wide variety of policy areas, such as data governance, content moderation, taxation, and labor law. Each one of these policy areas is composed of different policy instruments, such as “data protection regulation”, “content moderation regulation” and “merger control regulation”. The DPA database also groups interventions within “economic activities”. 

For the scope of this project - AI - we will analyze only interventions that affect the following economic activities, which make up the entire value chain of the artificial intelligence sector:

☁️ Infrastructure Providers: Cloud Computing, Storage and Databases - Entities offering cloud services, data storage, and database solutions. Examples: Amazon Web Services, Dropbox.
🤖 ML and AI Development Providers - Companies specializing in machine learning and artificial intelligence. Examples: OpenAI, Anthropic.
💻 Semiconductors - Companies in semiconductor development and manufacturing. Examples: NVIDIA, TSMC.

#### **2.1.3) Limitations from the datasets**
Each dataset present specific shortcomings that limit our ability to use them in order to answer our questions. On one hand, the GTA provides a clear categorization of policies according to their protectionist level, but does not separates them according to economic activity: since it is not focused on specific economic activities, one cannot reliable find which interventions related to the artificial intelligence sector. On the other hand, the DPA provides a clear definition of economic activity and is focused on policies pertaining to the digital world, but does not classify each of its interventions according to their protectionist level. As such, this project had to find a way to use information present in one dataset to infer missing data on the other. Section 3.2 will touch on this matter and propose a novel way to incorporate missing information on the DPA database.

## **3) Identifying protectionist policies through text analysis**
This project aims to study protectionist policies by using natural language processing tools. The first part of the project uses tools such as TF-IDF and Topic modeling to understand the patterns used in AI policy texts more broadly. Then, a text classification model was developed to identify specific protectionist AI policies. 

### 3.1) Exploratory analysis: Finding patterns in AI policy 
[The notebook is available here](https://github.com/brunokrp/ai-protectionism/blob/main/exploratory_analysis.ipynb)

#### 3.1.1) TF-IDF
TF-IDF (Term Frequency-Inverse Document Frequency) is a statistical tool that helps identify significant terms in a text corpus by balancing word frequency and uniqueness. In analyzing the descriptions of government interventions in the AI sector, TF-IDF can highlight terms associated with economic protectionism. I expect to find terms such as “tariffs,” “domestic prioritization,” or “export controls.” By comparing policy documents across countries, patterns can emerge, revealing recurring language tied to protecting local AI industries or limiting international competition. These patterns can provide valuable insights both into the economic motivations underlying AI policy decisions and the players that most commonly use such policies.

#### 1.2) Topic Modelling
Applying topic modeling to AI policy texts can reveal topics reflecting economic protectionism, like “domestic industry support” or “technology transfer restrictions.” By analyzing these topics, this paper aims to identify recurring concerns, such as safeguarding national AI capabilities or reducing reliance on foreign technology. Topic modeling also enables cross-country comparisons, highlighting differences in protectionist rhetoric. 

### 2) Identifying protectionist AI policies
As mentioned before, the DPA dataset has powerful features, but a crucial omission: it does not categorize interventions according to their level of protectionism. As such, the GTA dataset was used in order to fill in these missing information. To accurately identify the protectionist AI policies present in the DPA dataset, this project developed a custom text classification model fine-tuned on a pre-trained BERT (Bidirectional Encoder Representations from Transformers) model. The next two subsections describe this process in detail.

#### 2.1) Data mining intervention descriptions
[The notebook is available here](https://github.com/brunokrp/ai-protectionism/blob/main/model_classification.ipynb)
The Global Trade Alert dataset available for download in the institution's website only provides short descriptions about each intervention, which are insufficient to train a model to identify its main labels. Because of that, a data mining script was developed to webscrape each intervention available at the GTA website and save it to a separate file, alongside the label (red, amber or green). 

#### 2.2) Fine-tuning a distilBERT model
[The notebook is available here](https://github.com/brunokrp/ai-protectionism/blob/main/model_classification.ipynb)
Inspired by the approach taken by Juhász[2], policy texts labeled as protectionist (red) or non-protectionist (green or amber) were used to fine-tune a pre-trained model, enabling it to detect nuanced economic language patterns. Once fine-tuned, the model was applied to classify AI-related policy measures sourced from the Digital Policy Alert database. SHAP (SHapley Additive exPlanations) values were then utilized to explain individual predictions, attributing importance to specific features or phrases in the text. This step provided transparency into the model’s decisions, highlighting keywords or contextual cues that influenced protectionist classifications. Finally, GeoPandas - a Python library for geospatial data analysis - was used to visualize the distribution of protectionist AI policies globally on a world map, revealing regions with more significant concentrations of protectionist measures. 

## Results / Discussion



## Conclusions


## References
1. Reinert KA. Techno-Nationalism. In: The Lure of Economic Nationalism: Beyond Zero Sum. Anthem Press; 2023:137-156.
2. Juhász, R., Lane, N., Oehlsen, E., & Pérez, V. C. (2022). The who, what, when, and how of industrial policy: A text-based approach. What, When, and How of Industrial Policy: A Text-Based Approach (August 15, 2022).
3. 
