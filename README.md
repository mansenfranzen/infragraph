# Motivation

Handling complex cloud setups using Infrastructure as Code (IaC) tools like Terraform, CloudFormation, and Pulumi can be quite challenging. A key issue is presenting the current and future states of an infrastructure in a way that's clear and easy to understand for humans. Although the code and output files these tools generate are perfect for machines, they're not as user-friendly for cloud architects and developers. 

Usually, teams rely on architecture diagrams to visualize core infrastructure components like Virtual Private Clouds (VPCs), storage services (S3 buckets), and compute instances (EC2 machines). These diagrams are manually created and need regular updates to stay relevant, which is time-consuming and prone to errors. Moreover, these visualizations often miss critical details that are important for strategic planning and don't show changes over time, only static snapshots.

# Goal

Our objective is to create a software package that can interpret IaC data from various platforms (such as Terraform, CloudFormation, Pulumi) and convert it into a standardized graph format that can be easily explored and interacted with in a web browser. 

This software will have three main components:

1. **Backend**: This part will handle the extraction of information about cloud resources, including their relationships and properties, and map them into a graph structure.
2. **Graph Data Model**: This will define the way cloud resources are represented as nodes (points) and edges (connections) within our graph.
3. **Frontend**: This will allow users to interact with the graph data model dynamically. Features will include navigating the model, expanding and collapsing resource groups, and viewing detailed information about each component.

## Assumptions

- The cloud resources should be organized in a non-cyclic, hierarchical manner to maintain clarity in the visualization.

## Requirements

1. The software must reflect changes in the infrastructure, such as additions, updates, and deletions, as these are crucial for maintaining an accurate view. This change-awareness should be evident in the frontend visualizations.
2. It should allow users to manage the visibility of grouped resources, such as Terraform modules, which can be expanded or collapsed in the visual representation. This grouping should be consistent across all software layers.
3. The final visualization should be an interactive, standalone HTML/JavaScript file with features like zooming, collapsing groups, and hovering over elements to display tooltips with additional details.
4. Backend and frontend should be extensible adhering to a single, standardized interface to support new backends and frontends.

By simplifying these complex processes into a more intuitive and interactive format, we aim to improve the usability and accessibility of cloud infrastructure management for both technical and non-technical stakeholders.

# PoC

The initial version of this software package should only support Terraform as a backend.
