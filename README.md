# MAPPING AI PROTECTIONISM ACROSS THE WORLD

## **Artificial intelligence and economic nationalism**
There has been a perceptible uptick in global interest in two different, but complementary, topics: artificial intelligence (AI) and economic nationalism. 
AI has been, during the past few years, one of the most talked-about technologies in the world. From the 2010’s novel applications of deep and reinforcement learning to the recent innovation brought forth by large language models (GPT and other transformer architectures), the world’s eyes are paying close attention to the development of this technology. Not only are markets deploying valuable resources to further develop and use it, but governments have also taken considerable efforts to regulate and foster the artificial intelligence environment - semiconductors, data infrastructure, machine learning models, and its applications - foreseeing the potential risks and gains of such a ubiquitous technology. At the same time, the rise of economic nationalism is reshaping global trade dynamics. Economic nationalism is marked by policies prioritizing domestic industries over international cooperation, such as Trump's intentions to impose widespread tariffs on imports or the CHIPS Act, which aims to subsidize a revival of the U.S. semiconductor industry. These policies challenged decades of efforts to promote liberal trade. Simultaneously, international organizations like the World Trade Organization (WTO) have faced criticism for their inability to adapt to new economic realities or mediate disputes effectively. This failure has undermined trust in multilateral trade frameworks, prompting nations to pursue unilateral strategies that reflect growing skepticism toward globalization and free trade principles.
Both topics are now converging under the umbrella of the New Techno-nationalist movement. For this movement, the nation and its technologies must be defended through “protectionism measures, domestically supported manufacturing and technology, the rejection of multilateralism, the deployment of zero-sum narratives, and in some circumstances, ethnic discrimination”, as stated by Reinert. Such an argument contrasts with the liberal notions of free trade, international cooperation, and multiculturalism that made up much of the economic arguments of the last decades. Even more so when nationalistic arguments come from countries that were the winners of the free world - the US and Western Europe. 
This project has the objective of mapping the distribution of techno-nationalist AI policies throughout the world, identifying its leaders and the main policy instruments used by countries to enforce AI protectionism.

## **Data sources**
The Global Trade Alert (GTA) is a database that organizes information regarding governmental changes to market conditions. It first started in 2008 and has since then managed to store more than 70,000 governmental interventions. This reaction paper was based on this dataset because of the detailed taxonomy used to structure data about government interventions. One of the key attributes of this database is the categorization of each intervention according to the direction of the induced change: liberalizing or harmful toward foreign interests. GTA categorizes each intervention in one of three colors: 
🔴 Red - when the intervention almost certainly discriminates against foreign commercial interests;
🟠 Amber - when the intervention likely involves discrimination against foreign commercial interests;
🟢 Green - when the intervention liberalizes on a non-discriminatory (i.e., most favored nation) basis, or improves the transparency of a relevant policy.

The interventions described in the GTA are central to answering the questions posed in the introduction. The following sections describe the data and each level of analysis used.

## **Identifying protectionist policies through text analysis**
This project aims to identify protectionist policies by using natural language processing tools. The first part of the project uses tools such as TF-IDF and Topic modeling to understand the patterns used in AI policy texts more broadly. Then, a text classification model was developed to identify specific protectionist AI policies. 

### 1) Finding patterns in AI policy
#### 1.1) TF-IDF
TF-IDF (Term Frequency-Inverse Document Frequency) is a statistical tool that helps identify significant terms in a text corpus by balancing word frequency and uniqueness. In analyzing the descriptions of government interventions in the AI sector, TF-IDF can highlight terms associated with economic protectionism. I expect to find terms such as “tariffs,” “domestic prioritization,” or “export controls.” By comparing policy documents across countries, patterns can emerge, revealing recurring language tied to protecting local AI industries or limiting international competition. These patterns can provide valuable insights both into the economic motivations underlying AI policy decisions and the players that most commonly use such policies.

#### 1.2) Topic Modelling
Applying topic modeling to AI policy texts can reveal topics reflecting economic protectionism, like “domestic industry support” or “technology transfer restrictions.” By analyzing these topics, this paper aims to identify recurring concerns, such as safeguarding national AI capabilities or reducing reliance on foreign technology. Topic modeling also enables cross-country comparisons, highlighting differences in protectionist rhetoric. 

### 2) Identifying protectionist AI policies
To accurately identify protectionist AI policies, this project developed a custom text classification model fine-tuned on a pre-trained BERT (Bidirectional Encoder Representations from Transformers) model. Policy texts labeled as protectionist (red) or non-protectionist (green or amber) from the Global Trade Alert database were used to train the model, enabling it to detect nuanced economic language patterns. Once fine-tuned, the model was applied to classify AI-related policy measures sourced from the Digital Policy Alert database. SHAP (SHapley Additive exPlanations) values were then utilized to explain individual predictions, attributing importance to specific features or phrases in the text. This step provided transparency into the model’s decisions, highlighting keywords or contextual cues that influenced protectionist classifications, such as terms like "domestic preference," "foreign ownership limits," or "export restrictions."

To visualize the distribution of protectionist AI policies globally, the project employed GeoPandas, a Python library for geospatial data analysis. Policy classifications were plotted on a world map, revealing regions with significant concentrations of protectionist measures. These visualizations provided a geographical perspective, identifying clusters of protectionist policies, such as areas implementing data localization laws or offering subsidies to domestic AI industries. The map served as an intuitive tool to convey the extent of protectionist AI policies worldwide and their regional contexts. By combining machine learning, explainable AI, and geospatial analysis, this project offered a comprehensive approach to uncovering and interpreting patterns of economic protectionism in global AI policymaking.

## Results


## Conclusions


## References
1. Reinert KA. Techno-Nationalism. In: The Lure of Economic Nationalism: Beyond Zero Sum. Anthem Press; 2023:137-156.
2. Juhász, R., Lane, N., Oehlsen, E., & Pérez, V. C. (2022). The who, what, when, and how of industrial policy: A text-based approach. What, When, and How of Industrial Policy: A Text-Based Approach (August 15, 2022).
3. 
