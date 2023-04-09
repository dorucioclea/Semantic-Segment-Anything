<p align="center">
  <img src="./figures/logo.png" alt="SSA-1B Icon"/>
</p>

<h1 align="center">Semantic Segment Anything (SSA)</h1>

### [Tech report]()
> **Semantic Segment Anything**  
> Jiaqi Chen, Zeyu Yang, Li Zhang  
> Zhang Vision Group, Fudan Univerisity

Our _**S**emantic **S**egment **A**nything (SSA)_ project enhances the [Segment Anything dataset(SA-1B)](https://segment-anything.com/) 
by providing a powerful and effective annotation engine for large-scale semantic annotation.
We have developed an open framework that combines various semantic segmentation models, leveraging both open-source close-set segmentation algorithms and CLIP-based models. 
This framework facilitates the automated annotation of the SA-1B dataset with multiple semantic segmentation capabilities. We welcome feedback and discussions on this open framework, and encourage contributions from anyone with ideas or suggestions for further improvements.

### 🤔 Why do we need SSA?
- Although SA-1B is a large image segmentation dataset with fine mask segmentation annotations, it lacks semantic annotations for training.
- While advanced close-set segmenters such as Mask2Former and Upernet, open-set segmenters like CLIPSeg, and image caption methods like BLIP2 can provide rich semantic annotations, they often lack the ability to capture edges effectively.
- By combining the strengths of SA-1B's fine mask segmentation annotations with the rich semantic annotations provided by these advanced models, we can train more powerful models capable of semantic segmenting anything.
### 🚄 Semantic annotation engine
We have developed an automated annotation engine that assigns fine-grained category labels to object masks. The engine consists of two stages:
- **Step I**: Candidate Category Extraction: We leverage multiple advanced segmentation methods to extract candidate categories for each mask. Additionally, we use image captioning methods to provide richer candidate vocabulary for each local region.

- **Step II**: Global Category Assignment: After obtaining all candidate vocabulary for an image, we utilize open-world and open-vocabulary segmentation methods such as CLIPSeg to assign categories to each region. This enables us to obtain category labels for each mask.
### 📖 News
🔥 2023/04/09: The example of Semantic Segment Anything for SA-1B is released.
🔥 2023/04/05: SA-1B is released.  

## Examples
![](./figures/example.png)
## 💻 Requirements
- Python 3.7+
- mmcv-full 1.3.8
- mmdet 2.14.0
- transformers 4.6.1
## 🛠️ Get Started

```bash
pip intsall transformers
pip install spacy
python -m spacy download en_core_web_sm
git clone git@github.com:fudan-zvg/Semantic-Segment-Anything.git
cd Semantic-Segment-Anything
python models/classification/<method>.py
```
