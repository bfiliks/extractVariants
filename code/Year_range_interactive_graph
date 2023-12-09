# Load your data
df = pd.read_csv('modified_eda.csv')  # Replace with your file path

# Preprocess the data (as done previously)
df_filtered = df.dropna(subset=['Base_Text', 'variant_split'])
selected_year = range(1850, 1879)
df_selected = df_filtered[df_filtered['Year'].isin(selected_year)]
df_selected_no_duplicates = df_selected.drop_duplicates(subset=['Base_Text', 'variant_split'])

# Create a networkx graph
G = nx.Graph()
for _, row in df_selected_no_duplicates.iterrows():
    base_text = row['Base_Text']
    variant = row['variant_split']
    G.add_node(base_text, type='base_text')
    G.add_node(variant, type='variant')
    G.add_edge(base_text, variant)

# Position nodes using NetworkX
pos = nx.spring_layout(G, seed=42)

# Extract positions for Plotly
edge_x = []
edge_y = []
for edge in G.edges():
    x0, y0 = pos[edge[0]]
    x1, y1 = pos[edge[1]]
    edge_x.extend([x0, x1, None])
    edge_y.extend([y0, y1, None])

# Edge trace
edge_trace = go.Scatter(
    x=edge_x, y=edge_y,
    line=dict(width=0.5, color='#888'),
    hoverinfo='none',
    mode='lines')

# Node trace
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

# Create the figure
fig = go.Figure(data=[edge_trace, node_trace],
                layout=go.Layout(
                    title="Interactive Network Graph of Base_Text and Variant_Alternate",
                    showlegend=False,
                    hovermode='closest',
                    margin=dict(b=20,l=5,r=5,t=40),
                    xaxis=dict(showgrid=False, zeroline=False, showticklabels=False),
                    yaxis=dict(showgrid=False, zeroline=False, showticklabels=False)))

# Show the figure
fig.show()

# Save the figure as an HTML file
file_name = "interactive_graph.html"
fig.write_html(file_name)

# Download the file
from google.colab import files
files.download(file_name)
