## This is the code for Interactive Network Graph based on Fascicle range

import pandas as pd
import networkx as nx
import plotly.graph_objects as go

# Load your data
df = pd.read_csv('modified_eda.csv')  # Replace with your file path

# Filter for selected Fascicle_Number
selected_fascicles = range(1, 40)  # Fascicle numbers from 1 to 10
df_selected = df[df['Fascicle_Number'].isin(selected_fascicles)]

# Convert 'Base_Text' and 'variant_split' to strings and combine them
all_texts = df_selected['Base_Text'].astype(str) + ' ' + df_selected['variant_split'].astype(str)

# Split the combined texts into words and extract unique words
unique_words = set(word for text in all_texts for word in text.split())

# Create a graph
G = nx.Graph()
for word in unique_words:
    G.add_node(word)

# Define relationships between words
for text in all_texts:
    words = text.split()
    for i in range(len(words)):
        for j in range(i + 1, len(words)):
            G.add_edge(words[i], words[j])  # Add an edge between each pair of words

# Use a NetworkX layout to position nodes
pos = nx.spring_layout(G)

# Create the Plotly figure
fig = go.Figure(data=[edge_trace, node_trace],
                layout=go.Layout(
                    title="Interactive Network Graph of Words in Base_Text and Variant_Split",
                    showlegend=False,
                    hovermode='closest',
                    xaxis=dict(showgrid=False, zeroline=False, showticklabels=False),
                    yaxis=dict(showgrid=False, zeroline=False, showticklabels=False)))

# Render the figure
fig.show()

# Optionally, save to HTML
fig.write_html("your_interactive_word_graph.html")
# Download the file
from google.colab import files
files.download(file_name)
