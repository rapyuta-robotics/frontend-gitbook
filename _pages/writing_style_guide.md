---
title: Rapyuta Robotics Style Guide
author: Sachin
date: 2022-02-05
category: Jekyll
layout: post
---


## User Guide Formatting: Best Practices and Guidelines

This style guide provides guidelines for writing user guide documentation for Rapyuta Robotics. It aims to ensure consistency and readability across the documentation.

### Headings

- Use appropriate heading levels to structure the content.
- Use title case for all headings upto level 3
- Use sentence case for level 4 heading

  > **_NOTE:_**  Sentence case means capitalizing the first letter of the first word, and using lowercase for the remaining words, except for proper nouns and specific terms.

- Rule: The length of the underline must be at least as long as the title itself

    1.  `==========`  for title
    2.  `----------`  for the second level subsection
    3.  `~~~~~~~~~~`  for the third  level subsection
    4.  `""""""""""`  for the fourth level subsection

- Example:

  ```
  Title
  =====

  Second Level
  ------------

  Third Level
  ~~~~~~~~~~~
 
  Fourth level
  """""""""""""
  ```   

### Abbreviations and Acronyms

- Spell out abbreviations upon first mention, followed by the abbreviation in parentheses. 
- Use the abbreviation for subsequent mentions.

Example: "Rapyuta Robotics provides a Graphical User Interface (GUI) for easy navigation. The GUI offers various features..."


### Bold and Italics

- Use **bold** to highlight UI elements, buttons, menus selections, tabs, modal window. 
- Use *italics* when introducing new terms for the first time, page or screen names.
- When referring to a UI element, it is important to use the case as used in the actual user interface. 

### Code 

- Use `.. code-block::` directive to highlight and format code or command-line examples.
- Specify the language for syntax highlighting after the `::`. For example:
  
  ```
  ..  code-block:: json
      
      {
        "order_id": "20230101_order_data",
        "kind": "PICKING_WORKFLOW_ORDER_STATE",
        "data": {
          "state": "IN_PROGRESS",
          "prev_state": "ACCEPTED"
        },
        "created": "2023-01-01T00:00:00.000Z"
      }
  ```

### Inline Commands

Inline commands should be surrounded by double backticks ``

For example:

```
Events may be retrieved using the ``GET /v1/events/`` API endpoint.
```

### Links (internal and external)

- Example for linking to sections within the same document:

  ```
  This example :ref:`Cross-References to Locations in the Same Document`.
  ```

- Example for linking custom link text:
 
  ```
  This example links to a different :ref:`custom text<Heading Text>` section.
  ```

- Example for external links:

  ```
  This example links to an `external web page <link URL>`_.
  ```

### Figures

When including figures or images in the documentation, follow these guidelines:
- Use a meaningful alt text for accessibility.
- Use sentence case for figure names.

  > **_NOTE:_**  Sentence case means capitalizing the first letter of the first word, and using lowercase for the remaining words, except for proper nouns and specific terms.

- Include the custom `:class: figure-center-width-500` or `:class: figure-center-width-800` directive depending on the size of the image. This class will center align the image with width `500` or `800`. For example:

  ```
  .. figure:: path/to/figure.png
    :alt: Workflow Diagram
    :class: figure-center-width-500

    Figure: Workflow diagram
  ```

### Periods

- Use periods at the end of complete sentences (instructions, explanations, etc).
- Omit periods in sentence fragments or lists that are incomplete. For example:
  
  ```
  1. Select the desired item from the dropdown menu
  2. Adjust the slider to your preferred level
  3. Press the **Enter** key to confirm
  ```

- If the list item is a complete sentence or phrase, use "periods" at the end of each list item. For example:

  ```
  1. Turn on the device.
  2. Press the power button.
  3. Adjust the settings.
  ```

### Lists

#### Ordered Lists

- Use typically numbers (`1`, `2`, `3`, etc.) for ordered lists.
- Use sentence case for ordered lists.

#### Unordered Lists

- Use `-` for unordered lists.
- Use sentence case for unordered lists.

  > **_NOTE:_**  Sentence case means capitalizing the first letter of the first word, and using lowercase for the remaining words, except for proper nouns and specific terms.

#### When to use ordered and unordered lists?

**Ordered lists**: For sequential steps or instructions that must be followed in a specific order. For example:

```
1. Connect the power cable.
2. Press the power button.
3. Select your language.
4. Agree to the terms and conditions.
```

**Unordered lists**:  When you have a list of items that are not necessarily related in terms of order or priority, an unordered list is suitable. For example:

```
- Lightweight design
- Waterproof
- Long battery life
```

### Notes/Cautions/Admonitions

- The `.. note::` shortcode is used to display a note to the reader.
- The `.. note::` shortcode should be follow this syntax (line space, tab space). For example, 
  
  ```
   .. note::
        This is note text. Use a note for information you want the user to
        pay particular attention to.
  ```

- The `.. admonition::` shortcode is used when you want to use custom note titles.
  
  ```
  .. admonition:: The one with the custom titles

    This is a custom note.
  ```

### Tables

When creating tables, follow these guidelines:

- Use the appropriate RST syntax for creating tables.
- Include a clear and concise caption above the table, using sentence case (Prefix the table caption with "Table: Table Title")
- For table headers: use sentence case.
  
  > **_NOTE:_**  Sentence case means capitalizing the first letter of the first word, and using lowercase for the remaining words, except for proper nouns and specific terms.

- Include `:align: center` directive to align the table to center.
- There are two directives you can use for tables: `csv-table` and `list-table`. 

  - The `csv-table` directive allows you to import the data directly from a CSV file and render it as a table in your documentation. For example:

    ```
    .. csv-table:: Table: My CSV Table
       :file: my_table.csv
       :header-rows: 1
       :align: center
    ```

  - The `list-table` directive is used to manually define and specify the content of the table using RST syntax. For example:

    ```
    .. list-table:: Table: My List Table
       :widths: 20 30
       :header-rows: 1
       :align: center

       * - Column 1
         - Column 2
       * - Row 1
         - Cell 1,1
       * - Row 2
         - Cell 2,1
    ```

### Guidelines For a Pull Request (PR)

When creating a pull request in the documentation repository, please adhere to the following guidelines:

1. Add suitable **Wrike** links to the PR.

1. Add any **Slack communication** links or references for additional documentation links.

1. **Labels**: Ensure that you add the appropriate labels to your PR. Failure to add the necessary labels may result in the PR being rejected. Some recommended labels include:

   - `under_review`: for PRs that are currently under review.
   - `internal_spec`: for updates related to internal specifications.
   - `blocked`: for PRs that are blocked and awaiting further development.
   - `customer_spec`: for updates related to user-facing specifications.
   - `ready_to_merge`: for PRs that have completed the review process and are ready to be merged.
   - `new_user_doc`: for PRs that introduce changes to the structure of the user guide.
   - `adhoc`: for PRs that have adhoc documentaiton requests
   - `change_log`: for PRs that have release updates
   - `doc_improvements`: for PRs that have documentation (HTML & PDF) improvements related to styles, layouts, etc

1. **Commit Messages**: Use clear and meaningful commit messages. Consider following the conventional commit types for better organization:

   - `feat`: for adding new features or functionality to the documentation.
   - `fix`: for fixing issues or errors in the documentation.
   - `docs`: for making changes to the documentation that do not affect the code or functionality.
   - `chore`: for routine tasks or maintenance, such as updating dependencies or configurations.
   - `style`: for making changes to the formatting, styling, or presentation of the documentation.
   - `refactor`: for making structural or organizational changes to the documentation.
   - `test`: for adding or modifying tests for the documentation.


### Rapyuta Robotics Design System

Explore our branding guidelines, including colors, icons, and UI elements, and more in our comprehensive resource.

[Figma link](https://www.figma.com/file/AIbYRXbxFMYJOWCGzF8VIg/rr_design_system?type=design&node-id=808%3A3576&mode=design&t=CkEHMdR9mQdcBQeL-1).