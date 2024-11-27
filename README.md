# Dockerised Free-Bloom

This repository provides a Dockerised version of the [Free-Bloom](https://github.com/SooLab/Free-Bloom) project.

## Original Project

For the original codebase and additional information, please refer to the official repository:  
[Free-Bloom by SooLab](https://github.com/SooLab/Free-Bloom)

## Getting Started

### Prerequisites

- Docker installed on your machine.
- Access to a compatible GPU (NVIDIA recommended).

### Usage

To run the Dockerised version, use the following command:

```bash
./run.sh <gpu_id>
```

- Replace `<gpu_id>` with the ID of the GPU you want to use.  
  For example, use `0` for the default GPU.
- **Note:** Multi-GPU support is not configured, as it was not required for this implementation.

### Customizing Prompts

The file `data/test.json` contains a dictionary of prompts required for the model. Each key represents a **high-level prompt** (describing the overall animation), and the corresponding value is a **list of framewise prompts** (detailing the step-by-step progression of frames).  

Here is an example from `test.json`:

```json
{
    "A flower blooming from a bud to full bloom over time.": [
        "A tightly closed flower bud on a green stem.",
        "The bud begins to swell slightly.",
        "The bud enlarges, hinting at the petals inside.",
        "The tip of the bud starts to open slightly.",
        "Small gaps appear as petals begin to unfurl.",
        "Petals slowly emerge from the opening bud.",
        "More petals become visible as the bud opens further.",
        "The bud opens halfway, revealing vibrant petals.",
        "Petals continue to spread outward from the bud.",
        "The bud is now mostly open, with petals extending outward.",
        "The flower nears full bloom, petals nearly fully extended.",
        "The flower reaches full bloom with petals fully spread.",
        "The fully bloomed flower, vibrant and open.",
        "The flower in full bloom, petals wide open.",
        "A fully opened flower basking in the sunlight.",
        "The flower begins to lean slightly, petals fully open.",
        "Close-up of the fully bloomed flower's center.",
        "The flower's petals are wide open, displaying vivid colors.",
        "The flower sways gently with petals open.",
        "The flower's petals begin to curl slightly at the edges.",
        "The flower remains in full bloom, colors radiant.",
        "A side view of the fully bloomed flower.",
        "The flower stands tall, fully bloomed against the backdrop.",
        "The fully bloomed flower with petals spread wide open."
    ]
}
```

### How to Add Your Own Prompts

1. Open the `data/test.json` file in a text editor.
2. Add a new **high-level prompt** (e.g., `"A tree growing from a seedling to a full tree."`).
3. Provide a detailed list of **framewise prompts** that describe each step of the transformation.

For example:

```json
{
    "A tree growing from a seedling to a full tree.": [
        "A small seedling emerges from the soil.",
        "The seedling grows taller with a thin stem.",
        "Small leaves begin to sprout from the stem.",
        "The stem thickens and branches start to form.",
        "Leaves grow larger and become more numerous.",
        "The branches spread wider as the tree grows taller.",
        "The tree develops a thicker trunk with visible bark.",
        "The branches grow denser, with more leaves filling out.",
        "The tree takes on a fuller shape with vibrant green leaves.",
        "The fully grown tree stands tall with a broad canopy."
    ]
}
```

Save the file and re-run the script. The output animations will reflect your new prompts and framewise descriptions.

### Model Configuration

The model has been preconfigured with settings optimized to align with the recommendations from the original project.
