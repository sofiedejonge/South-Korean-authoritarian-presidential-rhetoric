# South-Korean-authoritarian-presidential-rhetoric
South Korean Authoritarian Presidential Rhetoric (1961–1992): A Computational Text Analysis

This project performs a computational text analysis on official South Korean presidential speeches delivered during a critical economic and political transition period (1961–1992). By combining Latent Dirichlet Allocation (LDA) topic modeling and dictionary-based sentiment analysis, this study examines how authoritarian and transitioning democratic regimes dynamically adapted their official discourse to secure political survival and manage domestic legitimacy crises.

Project Description
Official state discourse is a calculated political tool rather than a neutral reporting of events. This project analyzes a balanced corpus of 600 presidential speeches from three distinct administrations:
Park Chung-hee (1961–1979): Highly institutionalized military authoritarianism.
Chun Doo-hwan (1980–1988): Highly repressive military regime facing a severe domestic legitimacy deficit.
Roh Tae-woo (1988–1993): The critical transition era toward democratic consolidation.

Using the Orange Data Mining environment, the project applies pipelines to track the evolution of thematic trends (Topics) and emotional framing (Sentiment) across these three sequential political eras.

Research Question (RQ)
How did South Korean authoritarian presidents use rhetoric in their presidential speeches between 1961 and 1992? 

Headline Finding: 
Eight topics were identified during LDA topic modelling; Inter-Korean & U.S. Relations, Democratization & Globalization, National Security & Anti-communism, National Identity & Patriotism, Economic Industrialization, Social Movements & Civic Spirit, Bilateral Diplomacy, and International Relations & State visits. These themes were then analyzed to which president used most of which topic in their speeches. As a result, topic 3, 5, and 6 were mostly used by Park Chung-hee. Topics 4, and 7 were mostly used by Chun Doo-hwan, and topics 1, 2, and 7 were mostly used by Roh Tae-woo. Furthermore, while historical accounts record Chun Doo-hwan’s administration as the most brutal and repressive of the three, the computational sentiment analysis revealed a striking contradiction: Chun’s speeches contained the highest and most positive emotional sentiment by a substantial margin. This finding empirically exposes a key mechanism of authoritarian communication: Weaponized Optimism. Lacking democratic or developmental legitimacy, the Chun regime systematically deployed highly positive language to mask political coercion, project an artificial illusion of national harmony, and enforce social discipline. In contrast, the state's survival strategy shifted from Park's aggressive focus on existential threats (Anti-Communism and Industrialization) to Roh’s realistic negotiations of democratic pluralism (Democratic Globalism).

Instructions to Reproduce

Follow these steps to reproduce the topic modeling and sentiment analysis pipeline:

 1. Prerequisites & Environment Setup
* Download and install Orange Data Mining (v3.35 or higher recommended) from [orangedatamining.com](https://orangedatamining.com/).
* Open Orange and install the Text Mining Add-on via `Options` -> `Add-ons` -> Check `Text` -> Click `OK` (Restart Orange after installation).

2. Data Acquisition
* Clone or download the original corpus dataset containing the 600 speeches from the official GitHub repository: [https://github.com/scdenney/ba2-final-paper-data.git](https://github.com/scdenney/ba2-final-paper-data.git)

3. Text Preprocessing Pipeline Topic Modeling (LDA)
In your Orange canvas, construct the text mining pipeline using the following configurations:
1. Import Data: Load the speech corpus using the `file` widget.
2. Connect the ‘corpus’ widget.
3. Connect the python widget and upload the POS-based Kiwipiepy tokenization for Orange Data Mining. 
4. Connect the Python script to another ‘corpus’ widget, making sure the title variable is set to processed text.
5. Connect the corpus to the `Preprocess Text` widget and apply these exact settings:
    Tokenization: Whitespace tokenization.
    Filtering: Connect and upload the custom Korean stopword list to filter out non-semantic terms.

4. Running the Analyses
Connect the preprocessed text to the `Topic Modeling` widget. Set the algorithm to LDA (Latent Dirichlet Allocation) for 8 topics. Evaluate the cluster outputs. Connect this to a `Box Plot` to visualize mean scores across the different presidents.

3. Text Preprocessing Pipeline Sentiment Analysis
In your Orange canvas, construct the text mining pipeline using the following configurations:
1. Import Data: Load the speech corpus using the `file` widget.
2. Connect the ‘corpus’ widget.
3. Connect the python widget and upload the Kiwipiepy tokenization for sentiment analysis.
4. Connect the Python script to another ‘corpus’ widget, making sure the title variable is set to processed text.

4. Running the Analyses
 Connect the preprocessed text to the `Sentiment Analysis` widget. Select the multilingual sentiment, and upload the KNU Sentiment Lexicon. Connect the output to a `Box Plot` grouping by `President` to observe the emotional distribution.

Licence

Code:The source code and computation pipelines in this repository are licensed under the [MIT License](LICENSE) Data: Any newly produced data outputs, configurations, and analytical results generated in this project are licensed under a [Creative Commons Attribution 4.0 International License (CC-BY-4.0)](https://creativecommons.org/licenses/by/4.0/).
