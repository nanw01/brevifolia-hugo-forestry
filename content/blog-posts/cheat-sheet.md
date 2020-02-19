+++
author = "Nan"
date = ""
hero = "/images/c35d6bf83b89b50cdf2c48fa2b49614f.jpg"
title = "cheat sheet"
type = "blog"

+++
_#!/usr/bin/env python_

_# coding: utf-8_

  
_# In\[1\]:_  
  
_######################################### importing packages########################################_import pandas as pd _# data science essentials_import numpy as npimport matplotlib.pyplot as plt _# fundamental data visualization_import seaborn as sns _# enhanced visualizations_from sklearn.preprocessing import StandardScaler _# standard scaler_from sklearn.decomposition import PCA _# pca_from scipy.cluster.hierarchy import dendrogram, linkage _# dendrograms_from sklearn.cluster import KMeans _# k-means clustering_from sklearn.manifold import TSNE _# t-SNE_  
  
_# In\[2\]:_  
  
_######################################### loading data and setting display options######################################### loading data_survey_df = pd.read_excel('./dddd.xlsx')  
  
_# setting print options_pd.set_option('display.max_rows', 500)pd.set_option('display.max_columns', 500)pd.set_option('display.width', 1000)pd.set_option('display.max_colwidth', 100)  
  
  
survey_df.head()  
  
_# In\[3\]:_  
  
_######################################### inertia########################################_def **interia_plot**(data, max_clust = 8): """PARAMETERS----------data : DataFrame, data from which to build clusters. Dataset should be scaledmax_clust : int, maximum of range for how many clusters to check interia, default 50 """  
 ks = **range**(1, max_clust) inertias = \[\]  
  
 for k in ks: _# INSTANTIATING a kmeans object_ model = KMeans(n_clusters = k)  
  
 _# FITTING to the data_ model.fit(data)  
  
 _# append each inertia to the list of inertias_ inertias.append(model.inertia_)  
  
  
 _# plotting ks vs inertias_ fig, ax = plt.subplots(figsize = (12, 8)) plt.plot(ks, inertias, '-o')  
  
 _# labeling and displaying the plot_ plt.xlabel('number of clusters, k') plt.ylabel('inertia') plt.xticks(ks) plt.show()  
  
_######################################### scree_plot########################################_def **scree_plot**(pca_object, export = False): _# building a scree plot_  
 _# setting plot size_ fig, ax = plt.subplots(figsize=(10, 8)) features = **range**(pca_object.n_components_)  
  
 _# developing a scree plot_ plt.plot(features, pca_object.explained_variance_ratio_, linewidth = 2, marker = 'o', markersize = 10, markeredgecolor = 'black', markerfacecolor = 'grey')  
  
 _# setting more plot options_ plt.title('Scree Plot') plt.xlabel('PCA feature') plt.ylabel('Explained Variance') plt.xticks(features)  
 if export == True: _# exporting the plot_ plt.savefig('sample_survey_results.png') _# displaying the plot_ plt.show()  
  
_# In\[4\]:_  
  
survey_df.columns  
  
_# In\[5\]:_  
  
  
_# adaptive Thinking_adaptive_thinking = \[ 'See underlying patterns in complex situations', 'Don\\'t generate ideas that are new and different', 'Demonstrate an awareness of personal strengths and limitations', 'Display a growth mindset', 'Take initiative even when circumstances, objectives, or rules aren\\'t clear' \]_# 'Don\\'t generate ideas that are new and different'_  
_# relationship_relationship = \[ 'Build cooperative relationships', 'earn trust', 'Work well with people from diverse cultural backgrounds', 'Effectively negotiate interests, resources, and roles', 'Take initiative even when circumstances, objectives, or rules aren\\'t clear'\]  
  
_# teamwork_teamwork = \[ 'Can\\'t rally people on the team around a common goal', 'Seek and use feedback from teammates', 'Coach teammates for performance and growth', 'Resolve conflicts constructively'\]  
  
_# Execution_Execution = \[ 'Translate ideas into plans that are organized and realistic', 'Drive for results', 'Respond effectively to multiple priorities' \]  
_# communication_communication = \[ 'Encourage direct and open discussions', 'Listen carefully to others', 'Express ideas clearly', 'Don\\'t persuasively sell a vision or idea'\]_# 'Don\\'t persuasively sell a vision or idea'_  
  
_# In\[6\]:_  
  
p_5 = survey_df.loc\[:, \[ 'surveyID', 'Am the life of the party', 'Feel little concern for others','Am always prepared', 'Get stressed out easily', 'Have a rich vocabulary', 'Don\\'t talk a lot', 'Am interested in people', 'Leave my belongings around', 'Am relaxed most of the time', 'Have difficulty understanding abstract ideas', 'Feel comfortable around people', 'Insult people', 'Pay attention to details', 'Worry about things', 'Have a vivid imagination', 'Keep in the background', 'Sympathize with others\\' feelings', 'Make a mess of things', 'Seldom feel blue', 'Am not interested in abstract ideas', 'Start conversations', 'Am not interested in other people\\'s problems', 'Get chores done right away', 'Am easily disturbed', 'Have excellent ideas', 'Have little to say', 'Have a soft heart', 'Often forget to put things back in their proper place', 'Get upset easily', 'Do not have a good imagination', 'Talk to a lot of different people at parties', 'Am not really interested in others', 'Like order', 'Change my mood a lot', 'Am quick to understand things', 'Don\\'t like to draw attention to myself', 'Take time out for others', 'Shirk my duties', 'Have frequent mood swings', 'Use difficult words', 'Don\\'t mind being the center of attention', 'Feel others\\' emotions', 'Follow a schedule', 'Get irritated easily', 'Spend time reflecting on things', 'Am quiet around strangers', 'Make people feel at ease', 'Am exacting in my work', 'Often feel blue', 'Am full of ideas'\]\]p_5.shape  
  
_# In\[7\]:_  
  
_# E = 20 + (1) ___ - (6) ___ + (11) ___ - (16) ___ + (21) ___ - (26) ___ + (31) ___ - (36) ___ + (41) ___ - (46) ___ = _____# A = 14 - (2) ___ + (7) ___ - (12) ___ + (17) ___ - (22) ___ + (27) ___ - (32) ___ + (37) ___ + (42) ___ + (47) ___ = _____# C = 14 + (3) ___ - (8) ___ + (13) ___ - (18) ___ + (23) ___ - (28) ___ + (33) ___ - (38) ___ + (43) ___ + (48) ___ = _____# N = 38 - (4) ___ + (9) ___ - (14) ___ + (19) ___ - (24) ___ - (29) ___ - (34) ___ - (39) ___ - (44) ___ - (49) ___ = _____# O = 8 + (5) ___ - (10) ___ + (15) ___ - (20) ___ + (25) ___ - (30) ___ + (35) ___ + (40) ___ + (45) ___ + (50) ___ = ____  
big_personality_traits = pd.DataFrame()big_personality_traits\['surveyID'\] = p_5\['surveyID'\]  
big_personality_traits\['E'\] = 20 + p_5.iloc\[:, 1\] - p_5.iloc\[:, 6\] + p_5.iloc\[:,11\] - p_5.iloc\[:,16\] + p_5.iloc\[:,21\] - p_5.iloc\[:,26\] + p_5.iloc\[:,31\] - p_5.iloc\[:,36\] + p_5.iloc\[:,41\] - p_5.iloc\[:,46\]  
big_personality_traits\['A'\] = 14 - p_5.iloc\[:, 2\] + p_5.iloc\[:, 7\] - p_5.iloc\[:, 12\] + p_5.iloc\[:, 17\] - p_5.iloc\[:, 22\] + p_5.iloc\[:, 27\] - p_5.iloc\[:, 32\] + p_5.iloc\[:, 37\] + p_5.iloc\[:, 42\] + p_5.iloc\[:, 47\]  
big_personality_traits\['C'\] = 14 + p_5.iloc\[:, 3\] - p_5.iloc\[:, 8\] + p_5.iloc\[:,13\] - p_5.iloc\[:,18\] + p_5.iloc\[:,23\] - p_5.iloc\[:,28\] + p_5.iloc\[:,33\] - p_5.iloc\[:,38\] + p_5.iloc\[:,43\] + p_5.iloc\[:,48\] big_personality_traits\['N'\] = 38 - p_5.iloc\[:, 4\] + p_5.iloc\[:, 9\] - p_5.iloc\[:, 14\] + p_5.iloc\[:, 19\] - p_5.iloc\[:, 24\] - p_5.iloc\[:, 29\] - p_5.iloc\[:, 34\] - p_5.iloc\[:, 39\] - p_5.iloc\[:, 44\] - p_5.iloc\[:, 49\]big_personality_traits\['O'\] = 8 + p_5.iloc\[:, 5\] - p_5.iloc\[:,10\] + p_5.iloc\[:,15\] - p_5.iloc\[:,20\] + p_5.iloc\[:,25\] - p_5.iloc\[:,30\] + p_5.iloc\[:,35\] + p_5.iloc\[:,40\] + p_5.iloc\[:,45\] + p_5.iloc\[:,50\]   
  
**print**(big_personality_traits.shape)big_personality_traits.head()  
  
_# In\[8\]:_  
  
  
big_5 = big_personality_traits.drop('surveyID',axis=1)  
scaler = StandardScaler()X_scaled = scaler.fit_transform(big_5)big_5_scaled = pd.DataFrame(X_scaled)  
  
big_5_scaled.columns = big_5.columns  
  
_# checking pre- and post-scaling variance_**print**(np.var(big_5), '\\n\\n')**print**(np.var(big_5_scaled))  
  
_# In\[9\]:_  
  
_# PCA_  
_# INSTANTIATING a PCA object with no limit to principal components_pca = PCA(n_components = None, random_state = 802)  
  
_# FITTING and TRANSFORMING the purchases_scaled_survey_pca = pca.fit_transform(big_5_scaled)  
  
_# calling the scree_plot function_scree_plot(pca_object = pca)   
  
_# In\[10\]:_  
  
_# PCA_  
_# INSTANTIATING a PCA object with no limit to principal components_pca_custom = PCA(n_components = 3, random_state = 802)  
  
_# FITTING and TRANSFORMING the purchases_scaled_survey_pca = pca_custom.fit_transform(big_5_scaled)  
  
_# calling the scree_plot function_scree_plot(pca_object = pca_custom)   
  
_# In\[11\]:_  
  
_####################### Max PC Model ######################## transposing pca components (pc = MAX)_factor_loadings = pd.DataFrame(np.transpose(pca.components_))  
  
_# naming rows as original features_factor_loadings = factor_loadings.set_index(big_5_scaled.columns)  
  
_##################### 3 PC Model ###################### transposing pca components (pc = 3)_factor_loadings_custom = pd.DataFrame(np.transpose(pca_custom.components_))  
  
_# naming rows as original features_factor_loadings_custom = factor_loadings_custom.set_index(big_5_scaled.columns)  
  
_# checking the results_**print**(f"""MAX Components Factor Loadings------------------------------{factor_loadings.round(2)}  
  
3 Components Factor Loadings------------------------------{factor_loadings_custom.round(2)}""")  
  
_# In\[12\]:_  
  
  
PCA_components = pd.DataFrame(survey_pca)  
  
PCA_components.columns = \['V_' + str(i) for i in **range**(PCA_components.shape\[1\])\]  
_# import plotly.express as px# df = px.data.iris()# fig = px.scatter_3d(PCA_components, x='V1', y='V2', z='V3')# fig.show()_  
_# PCA_components.set_index(big_5.columns)_  
  
_# In\[13\]:_  
  
PCA_components.head()  
  
_# In\[14\]:_  
  
_# Scaler again_  
_# INSTANTIATING a StandardScaler() object_scaler = StandardScaler()X_scaled_pca = scaler.fit_transform(PCA_components)  
pca_scaled = pd.DataFrame(X_scaled_pca)pca_scaled.columns = \[ 'V_' + str(i) for i in **range**(pca_scaled.shape\[1\])\]  
**print**(np.var(PCA_components), '\\n\\n')**print**(np.var(pca_scaled))  
  
_# In\[15\]:_  
  
  
  
_# grouping data based on Ward distance_standard_mergings_ward = linkage(y = pca_scaled, method = 'ward')  
  
_# setting plot size_fig, ax = plt.subplots(figsize=(12, 12))  
_# developing a dendrogram_dendrogram(Z = standard_mergings_ward, leaf_rotation = 90, leaf_font_size = 6)  
  
_# saving and displaying the plot_plt.savefig('standard_hierarchical_clust_ward.png')plt.show()  
  
  
_# In\[16\]:_  
  
  
  
  
  
_# calling the inertia_plot() function_interia_plot(data = pca_scaled,max_clust= 7)  
  
_# In\[17\]:_  
  
  
_# INSTANTIATING a k-Means object with five clusters_customers_k_pca = KMeans(n_clusters = 4, random_state = 802)  
  
_# fitting the object to the data_customers_k_pca.fit(pca_scaled)  
  
_# converting the clusters to a DataFrame_customers_kmeans_pca = pd.DataFrame({'Big_5_Cluster': customers_k_pca.labels_})  
  
_# checking the results_**print**(customers_kmeans_pca.iloc\[: , 0\].value_counts())customers_kmeans_pca.head(5)  
  
_# In\[18\]:_  
  
  
_# storing cluster centers_centroids_pca = customers_k_pca.cluster_centers_  
  
_# converting cluster centers into a DataFrame_centroids_pca_df = pd.DataFrame(centroids_pca)  
_# renaming principal components_centroids_pca_df.columns = \[ 'V_' + str(i) for i in **range**(centroids_pca_df.shape\[1\])\]  
_# checking results (clusters = rows, pc = columns)_centroids_pca_df.round(2)  
  
_# In\[19\]:_  
  
_# add label_  
  
clst_pca_df = pd.concat(\[survey_df.loc\[ : , \['surveyID', 'What laptop do you currently have?', 'What laptop would you buy in next assuming if all laptops cost the same?', 'What program are you in?', 'What is your age?', 'Gender', 'What is your nationality? ', 'What is your ethnicity?'\]\], customers_kmeans_pca\], axis = 1)  
  
clst_pca_df.head(10)  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_  
  
  
  
  
_# In\[20\]:_  
  
  
_# adaptive Thinking_adaptive_thinking = \[ 'See underlying patterns in complex situations', 'Don\\'t generate ideas that are new and different', 'Demonstrate an awareness of personal strengths and limitations', 'Display a growth mindset', 'Take initiative even when circumstances, objectives, or rules aren\\'t clear' \]_# 'Don\\'t generate ideas that are new and different'_  
_# relationship_relationship = \[ 'Build cooperative relationships', 'Work well with people from diverse cultural backgrounds', 'Effectively negotiate interests, resources, and roles', 'Take initiative even when circumstances, objectives, or rules aren\\'t clear'\]  
  
_# teamwork_teamwork = \[ 'Can\\'t rally people on the team around a common goal', 'Seek and use feedback from teammates', 'Coach teammates for performance and growth', 'Resolve conflicts constructively'\]  
  
_# Execution_execution = \[ 'Translate ideas into plans that are organized and realistic', 'Drive for results', 'Respond effectively to multiple priorities'\]  
_# communication_communication = \[ 'Encourage direct and open discussions', 'Listen carefully to others', 'Don\\'t persuasively sell a vision or idea'\]_# 'Don\\'t persuasively sell a vision or idea'_  
  
_# In\[21\]:_  
  
survey_df\[communication\]  
  
_# In\[22\]:_  
  
hult_dna = pd.DataFrame()  
hult_df = survey_df.copy()  
hult_df\['Don\\'t generate ideas that are new and different'\] = 6 - survey_df\['Don\\'t generate ideas that are new and different'\]hult_df\['Don\\'t persuasively sell a vision or idea'\] = 6 - survey_df\['Don\\'t persuasively sell a vision or idea'\]  
  
  
for i,j in hult_df.iterrows(): adaptive_thinking hult_dna.loc\[i,'adaptive_thinking'\] = survey_df.loc\[i,adaptive_thinking\].mean() hult_dna.loc\[i,'communication'\] = survey_df.loc\[i,communication\].mean() hult_dna.loc\[i,'relationship_building'\] = survey_df.loc\[i,relationship\].mean() hult_dna.loc\[i,'teamwork'\] = survey_df.loc\[i,teamwork\].mean() hult_dna.loc\[i,'execution'\] = survey_df.loc\[i,execution\].mean()   
hult_dna.shape   
  
_# In\[23\]:_  
  
hult_dna = pd.concat(\[hult_df\['surveyID'\],hult_dna\],axis=1)hult_dna.head()  
  
_# In\[24\]:_  
  
  
hult_dna = hult_dna.drop('surveyID',axis=1)  
scaler = StandardScaler()X_scaled = scaler.fit_transform(hult_dna)hult_dna_scaled = pd.DataFrame(X_scaled)  
  
hult_dna_scaled.columns = hult_dna.columns  
  
_# checking pre- and post-scaling variance_**print**(np.var(hult_dna), '\\n\\n')**print**(np.var(hult_dna_scaled))  
  
_# In\[25\]:_  
  
_# PCA_  
_# INSTANTIATING a PCA object with no limit to principal components_hult_dna_pca = PCA(n_components = None, random_state = 802)  
  
_# FITTING and TRANSFORMING the purchases_scaled_hult_dna_pca_0 = hult_dna_pca.fit_transform(hult_dna_scaled)  
  
_# calling the scree_plot function_scree_plot(pca_object = hult_dna_pca)   
  
_# In\[26\]:_  
  
_# PCA_  
_# INSTANTIATING a PCA object with no limit to principal components_hult_dna_pca_custom = PCA(n_components = 3, random_state = 802)  
  
_# FITTING and TRANSFORMING the purchases_scaled_hult_dna_pca_custom_0 = hult_dna_pca_custom.fit_transform(hult_dna_scaled)  
  
_# calling the scree_plot function_scree_plot(pca_object = hult_dna_pca_custom)   
  
_# In\[27\]:_  
  
_####################### Max PC Model ######################## transposing pca components (pc = MAX)_factor_loadings = pd.DataFrame(np.transpose(hult_dna_pca.components_))  
  
_# naming rows as original features_factor_loadings = factor_loadings.set_index(hult_dna_scaled.columns)  
  
_##################### 3 PC Model ###################### transposing pca components (pc = 3)_factor_loadings_custom = pd.DataFrame(np.transpose(hult_dna_pca_custom.components_))  
  
_# naming rows as original features_factor_loadings_custom = factor_loadings_custom.set_index(hult_dna_scaled.columns)  
  
_# checking the results_**print**(f"""MAX Components Factor Loadings------------------------------{factor_loadings.round(2)}  
  
3 Components Factor Loadings------------------------------{factor_loadings_custom.round(2)}""")  
  
_# In\[28\]:_  
  
  
Hult_DNA_PCA_components = pd.DataFrame(hult_dna_pca_custom_0)  
  
Hult_DNA_PCA_components.columns = \['hult_dna_' + str(i) for i in **range**(PCA_components.shape\[1\])\]  
_# import plotly.express as px# df = px.data.iris()# fig = px.scatter_3d(PCA_components, x='V1', y='V2', z='V3')# fig.show()_  
_# PCA_components.set_index(big_5.columns)_  
  
_# In\[29\]:_  
  
Hult_DNA_PCA_components.head()  
  
_# In\[30\]:_  
  
_# Scaler again_  
_# INSTANTIATING a StandardScaler() object_scaler = StandardScaler()X_scaled_pca = scaler.fit_transform(Hult_DNA_PCA_components)  
pca_scaled = pd.DataFrame(X_scaled_pca)pca_scaled.columns = \[ 'V_' + str(i) for i in **range**(hult_dna_pca_custom_0.shape\[1\])\]  
**print**(np.var(Hult_DNA_PCA_components), '\\n\\n')**print**(np.var(hult_dna_pca_custom_0))  
  
_# In\[31\]:_  
  
  
  
_# grouping data based on Ward distance_standard_mergings_ward = linkage(y = hult_dna_pca_custom_0, method = 'ward')  
  
_# setting plot size_fig, ax = plt.subplots(figsize=(12, 12))  
_# developing a dendrogram_dendrogram(Z = standard_mergings_ward, leaf_rotation = 90, leaf_font_size = 6)  
  
_# saving and displaying the plot_plt.savefig('standard_hierarchical_clust_ward.png')plt.show()  
  
  
_# In\[32\]:_  
  
  
_# calling the inertia_plot() function_interia_plot(data = hult_dna_pca_custom_0,max_clust= 7)  
  
_# In\[33\]:_  
  
  
_# INSTANTIATING a k-Means object with five clusters_customers_k_pca = KMeans(n_clusters = 4, random_state = 802)  
  
_# fitting the object to the data_customers_k_pca.fit(hult_dna_pca_custom_0)  
  
_# converting the clusters to a DataFrame_customers_kmeans_pca = pd.DataFrame({'Hult_DNA_Cluster': customers_k_pca.labels_})  
  
_# checking the results_**print**(customers_kmeans_pca.iloc\[: , 0\].value_counts())customers_kmeans_pca.head(5)  
  
_# In\[34\]:_  
  
  
_# storing cluster centers_centroids_pca = customers_k_pca.cluster_centers_  
  
_# converting cluster centers into a DataFrame_centroids_pca_df = pd.DataFrame(centroids_pca)  
_# renaming principal components_centroids_pca_df.columns = \[ 'hult_' + str(i) for i in **range**(centroids_pca_df.shape\[1\])\]  
_# checking results (clusters = rows, pc = columns)_centroids_pca_df.round(2)  
  
_# In\[35\]:_  
  
_# add label_  
  
clst_pca_df = pd.concat(\[clst_pca_df,customers_kmeans_pca\], axis = 1)  
  
clst_pca_df.head(10)  
  
_# In\[ \]:_  
  
  
  
  
_# In\[ \]:_