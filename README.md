# Intra-Inter Relationship Modeling Network: toward Food Semantic Segmentation in Multi Foreground Scenes


This is the official implementation of the paper "[Intra-Inter Relationship Modeling Network: toward Food Semantic Segmentation in Multi Foreground Scenes]". 
The source code will be made publicly available upon the paper's acceptance.

---

We propose the Intra-Inter Relationship Modeling Network (IIRM-Net), a novel framework specifically designed for food semantic segmentation. IIRM-Net builds upon existing mask-based segmentation paradigms and introduces two key advancements. First, it enhances contextual understanding by explicitly modeling intra-category spatial dependencies and inter-category semantic correlations, enabling more coherent predictions in complex multi-foreground food scenes. Specifically, an Adaptive-distance Dependency Block (AdDB) is introduced to capture long-range relationships within each food category while maintaining computational efficiency, and a Category Correlation Modeling (CCM) module is designed to learn co-occurrence patterns among different food categories for improved classification consistency. Second, it improves boundary discrimination through an intra-inter boundary modeling strategy, where instance-wise boundary supervision is combined with enriched inter-object boundary interactions. This is achieved via a Contextual-geometric Boundary Supervision (CgBS) mechanism, which strengthens fine-grained boundary awareness and improves segmentation quality in overlapping or adjacent regions. Overall, these designs allow IIRM-Net to produce more accurate and structurally consistent segmentation results across diverse food scenes while maintaining efficiency.
  <img src="pic/vis.jpg" />

Our IIRM-Net architecture is mainly composed of several components: the backbone, the pixel decoder, the Adaptive-distance Dependency Block (AdDB), the Category Correlation Modeling (CCM) module, the Contextual-geometric Boundary Supervision (CgBS) strategy, and the post-processing stage. The AdDB module is designed to capture long-range intra-category dependencies efficiently, improving spatial consistency within each food instance. The CCM module focuses on modeling inter-category relationships to refine class predictions based on contextual co-occurrence. Furthermore, the CgBS strategy enhances boundary supervision by incorporating both instance-wise boundary prediction and inter-instance geometric interactions, contributing to more precise segmentation in complex and overlapping food regions.

  <img src="pic/pic_overall15.pdf" />

## Installation

Please follow our [installation.md](installation.md) to install.


## <a name="GettingStarted"></a>Getting Started

### Train & Evaluation
To train a model with "train_net.py", use
```
python train_net.py  --config-file /path/to/config
```
To evaluate a model's performance, use
```
python train_net.py --config-file /path/to/config --eval-only MODEL.WEIGHTS /path/to/checkpoint_file
```

## Quantitative results

<table>
  <tr>
    <th rowspan="2">Method</th> 
    <th colspan="3">FoodSeg103</th> 
    <th colspan="3">UECFoodPixComplete</th> 
    <th colspan="3">Food50Seg</th> 
  </tr>
  <tr>
    <td>mIou</td>
    <td>mAcc</td>
    <td>aAcc</td>
    <td>mIou</td>
    <td>mAcc</td>
    <td>aAcc</td>
    <td>mIou</td>
    <td>mAcc</td>
    <td>aAcc</td>
  </tr>


  <tr>
    <td>Mask2Former</td>
    <td> 51.37</td>
    <td> 85.91</td>
    <td>62.85 </td>
    <td>68.39</td>
    <td>89.34</td>
    <td>78.68</td>
    <td>92.77</td>
    <td>96.45</td>
    <td>96.17</td>
  </tr>

  <tr>
    <td>DEMaskNet</td>
    <td> 52.87</td>
    <td>86.40</td>
    <td>64.39</td>
    <td>70.12</td>
    <td> 89.78</td>
    <td> 81.32</td>
    <td>93.32</td>
    <td>96.70</td>
    <td>97.74</td>
  </tr>
</table>

The data in the table is still subject to updates.


## License

The model is licensed under the [Apache 2.0 license](LICENSE).

## Citation

We will provide the citation after the paper is published.
