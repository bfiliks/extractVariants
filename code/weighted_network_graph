## Code for calculating Weighted Network Graph of Word Co_Occurrence in EDA

import pandas as pd
import networkx as nx
import plotly.graph_objects as go
from collections import defaultdict

# Load your data
df = pd.read_csv('modified_eda.csv')  # Replace with your file path

# Filter for selected Fascicle_Number
selected_fascicles = range(1, 11)  # Fascicle numbers from 1 to 10
df_selected = df[df['Fascicle_Number'].isin(selected_fascicles)]

# Combine 'Base_Text' and 'variant_split' and convert to strings
all_texts = df_selected['Base_Text'].astype(str) + ' ' + df_selected['variant_split'].astype(str)

# Count word pairs
word_pairs = defaultdict(int)
for text in all_texts:
    words = text.split()
    for i in range(len(words)):
        for j in range(i + 1, len(words)):
            pair = tuple(sorted([words[i], words[j]]))
            word_pairs[pair] += 1

# Create a weighted graph
G = nx.Graph()
for (word1, word2), weight in word_pairs.items():
    G.add_edge(word1, word2, weight=weight)

# Use a NetworkX layout to position nodes
pos = nx.spring_layout(G)

# Create Plotly traces for the graph
edge_traces = []
for edge in G.edges(data=True):
    x0, y0 = pos[edge[0]]
    x1, y1 = pos[edge[1]]
    weight = edge[2]['weight']
    edge_trace = go.Scatter(
        x=[x0, x1, None], y=[y0, y1, None],
        line=dict(width=weight * 0.5, color='#888'),  # Adjust line width based on weight
        hoverinfo='none',
        mode='lines')
    edge_traces.append(edge_trace)

node_x = []
node_y = []
node_text = []
for node in G.nodes():
    x, y = pos[node]
    node_x.append(x)
    node_y.append(y)
    node_text.append(node)

node_trace = go.Scatter(
    x=node_x, y=node_y,
    mode='markers',
    hoverinfo='text',
    text=node_text,
    marker=dict(
        showscale=False,
        size=10,
        line_width=2))

# Create the Plotly figure
fig = go.Figure(data=edge_traces + [node_trace],
                layout=go.Layout(
                    title="Weighted Network Graph of Word Co-Occurrences",
                    showlegend=False,
                    hovermode='closest',
                    xaxis=dict(showgrid=False, zeroline=False, showticklabels=False),
                    yaxis=dict(showgrid=False, zeroline=False, showticklabels=False)))

# Render the figure
fig.show()

# Optionally, save to HTML
file_name = "your_interactive_word_graph.html"  # Define the file name
fig.write_html(file_name)

# Download the file
from google.colab import files
files.download(file_name)
