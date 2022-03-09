# <p align=center>`awesome neural rendering`</p>
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity) [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com) [![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)
<!-- [![Documentation Status](https://readthedocs.org/projects/ansicolortags/badge/?version=latest)](http://ansicolortags.readthedocs.io/?badge=latest) -->

A collection of resources on neural rendering. 

## Contributing

If you think I have missed out on something (or) have any suggestions (papers, implementations and other resources), feel free to [pull a request](https://github.com/xiaweihao/awesome-image-translation/pulls). Feedback and contributions are welcome!

markdown format:
``` markdown
**Here is the Paper Name.**<br>
*[Author 1](homepage), Author 2, and Author 3.*<br>
Conference or Journal Year. [[PDF](link)] [[Project](link)] [[Github](link)] [[Video](link)] [[Data](link)]
```

<details><summary>Table of Contents</summary><p>

- [Intruduction of Neural Rendering](#intruduction-of-neural-rendering)
- [Related Surveys and Course Notes](#related-surveys-and-course-notes)
- [Inverse Rendering (de-rendering)](#inverse-rendering--de-rendering-)
- [Neural Rerendering](#neural-rerendering)
- [Differentiable Rendering](#differentiable-rendering)
- [Volumetric Performance Capture (Free Viewpoint Video)](#volumetric-performance-capture--free-viewpoint-video-)
- [Semantic Photo Synthesis and Manipulation](#semantic-photo-synthesis-and-manipulation)
- [Texture and Surface Embedding or Mapping](#texture-and-surface-embedding-or-mapping)
- [Implicit Neural Scene Representation and Rendering](#implicit-neural-scene-representation-and-rendering)
- [Novel-View Synthesis for Objects and Scenes](#novel-view-synthesis-for-objects-and-scenes)
- [Light, Reflectance, Illuminance, and Shade](#light--reflectance--illuminance--and-shade)
- [Dubbing and Talking-Head Animation](#dubbing-and-talking-head-animation)
- [Motion Transfer, Retargeting, and Reenactment](#motion-transfer--retargeting--and-reenactment)
</p></details><p></p>

## Intruduction of Neural Rendering

**Neural Rendering** is a new and rapidly emerging field that combines generative machine learning techniques with physical knowledge from computer graphics, e.g., by the integration of differentiable rendering into network training. 

Ayush Tewari et. al. define **Neural Rendering** as

> <p align="justify"> <i>Deep image or video generation approaches that enable explicit or implicit control of scene properties such as illumination, camera parameters, pose, geometry, appearance, and semantic structure.</i></p>

A typical neural rendering approach takes as input images corresponding to certain scene conditions (for example, viewpoint, lighting, layout, etc.), builds a “neural” scene representation from them, and “renders” this representation under novel scene properties to synthesize novel images.

CVPR 2020 tutorial define **Neural Rendering** as
> <p align="justify"> <i>Neural rendering is a new class of deep image and video generation approaches that enable explicit or implicit control of scene properties such as illumination, camera parameters, pose, geometry, appearance, and semantic structure. It combines generative machine learning techniques with physical knowledge from computer graphics to obtain controllable and photo-realistic outputs.</i></p>

Given high-quality scene specifications, **Classic Rendering Methods** can render photorealistic images for a variety of complex real-world phenomena. Moreover, rendering gives us explicit editing control over all the elements of the scene-camera viewpoint, lighting, geometry and materials. However, building high-quality scene models, especially directly from images, requires significant manual effort, and automated scene modeling from images is an open research problem. On the other hand, **Deep Generative Networks** are now starting to produce visually compelling images and videos either from random noise, or conditioned on certain user specifications like scene segmentation and layout. However, they do not yet allow for fine-grained control over scene appearance and cannot always handle the complex, non-local, 3D interactions between scene properties. In contrast, neural rendering methods hold the promise of combining these approaches to enable controllable, high-quality synthesis of novel images from input images/videos. 

## Related Surveys and Course Notes

**[State of the Art on Neural Rendering.](https://arxiv.org/abs/2004.03805)**<br>
*Ayush Tewari, Ohad Fried, Justus Thies, Vincent Sitzmann, Stephen Lombardi, Kalyan Sunkavalli, Ricardo Martin-Brualla, Tomas Simon, Jason Saragih, Matthias Nießner, Rohit Pandey, Sean Fanello, Gordon Wetzstein, Jun-Yan Zhu, Christian Theobalt, Maneesh Agrawala, Eli Shechtman, Dan B Goldman, Michael Zollhöfer.*<br>
Eurographics 2020.<br>

**[Advances in Neural Rendering.]()**<br>
*Ayush Tewari, Justus Thies, Ben Mildenhall, Pratul Srinivasan, Edgar Tretschk, Yifan Wang, Christoph Lassner, Vincent Sitzmann, Ricardo Martin-Brualla, Stephen Lombardi, Tomas Simon, Christian Theobalt, Matthias Niessner, Jonathan T. Barron, Gordon Wetzstein, Michael Zollhoefer, Vladislav Golyanik.*<br>
ACM SIGGRAPH 2021 Courses. [[PDF](https://arxiv.org/abs/2111.05849)]

**[CVPR 2020 tutorial on Neural Rendering.](https://www.neuralrender.com/)**<br>
*Ayush Tewari, Ohad Fried, Justus Thies, Vincent Sitzmann, Stephen Lombardi, Kalyan Sunkavalli, Ricardo Martin-Brualla, Tomas Simon, Jason Saragih, Matthias Nießner, Rohit K. Pandey, Sean Fanello, Gordon Wetzstein, Jun-Yan Zhu, Christian Theobalt, Maneesh Agrawala, Eli Shechtman, Dan B. Goldman, Michael Zollhöfer.*<br>

**[Differentiable Rendering: A Survey.](https://arxiv.org/abs/2006.12057)**<br>
*Hiroharu Kato, Deniz Beker, Mihai Morariu, Takahiro Ando, Toru Matsuoka, Wadim Kehl, Adrien Gaidon.*<br>

## Inverse Rendering (de-rendering)

**De-rendering 3D Objects in the Wild.**<br>
*Felix Wimbauer, Shangzhe Wu, Christian Rupprecht.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2201.02279)]

**Unified Shape and SVBRDF Recovery using Differentiable Monte Carlo Rendering.**<br>
*[Fujun Luan](https://www.cs.cornell.edu/~fujun/), [Shuang Zhao](https://www.shuangz.com/), [Kavita Bala](https://www.cs.cornell.edu/~kb/), [Zhao Dong](http://flycooler.com/).*<br>
EGSR 2021. [[PDF](https://www.cs.cornell.edu/~fujun/files/egsr2021/paper.pdf)] [[Project](https://luanfujun.github.io/InverseMeshSVBRDF/)] [[Video](https://youtu.be/u9HqKGqvJhQ?t=8404)]

**PhySG: Inverse Rendering with Spherical Gaussians for Physics-based Material Editing and Relighting.**<br>
*Kai Zhang, Fujun Luan, Qianqian Wang, Kavita Bala, Noah Snavely.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2104.00674)] [[Project](https://kai-46.github.io/PhySG-website/)]

**Invertible Neural BRDF for Object Inverse Rendering.**<br>
*Zhe Chen, Shohei Nobuhara, Ko Nishino.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2008.04030)]

**Inverse Rendering for Complex Indoor Scenes: Shape, Spatially-Varying Lighting and SVBRDF From a Single Image.**<br>
*[Zhengqin Li](http://sites.google.com/a/eng.ucsd.edu/zhengqinli/), [Mohammad Shafiei](https://www.linkedin.com/in/mohammadshafiei/), [Ravi Ramamoorthi](http://cseweb.ucsd.edu/~ravir/), [Kalyan Sunkavalli](http://www.kalyans.org/), [Manmohan Chandraker](http://cseweb.ucsd.edu/~mkchandraker/).*<br>
CVPR 2020.[[PDF](https://drive.google.com/file/d/18zG1kzVpL9XsEVBK95hbpnB-FMlChRXP/view?usp=sharing)] [[Project](http://cseweb.ucsd.edu/~viscomp/projects/CVPR20InverseIndoor/)] [[Github](https://github.com/lzqsd/InverseRenderingOfIndoorScene)]

**Polarimetric Multi-View Inverse Rendering.**<br>
*Jinyu Zhao, Yusuke Monno, Masatoshi Okutomi.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2007.08830)]

**NiLBS: Neural Inverse Linear Blend Skinning.**<br>
*Timothy Jeruzalski, David I.W. Levin, Alec Jacobson, Paul Lalonde, Mohammad Norouzi, Andrea Tagliasacchi.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2004.05980)]

**Learning to Predict 3D Objects with an Interpolation-based Differentiable Renderer.**<br>
*Wenzheng Chen, Jun Gao, Huan Ling, Edward J. Smith, Jaakko Lehtinen, Alec Jacobson, Sanja Fidler.*<br>
NeurIPS 2019. [[PDF](https://arxiv.org/abs/1908.01210)]

**DRWR: A Differentiable Renderer without Rendering for Unsupervised 3D Structure Learning from Silhouette Images.**<br>
*Zhizhong Han, Chao Chen, Yu-Shen Liu, Matthias Zwicker.*<br>
ICML 2020. [[PDF](https://arxiv.org/abs/2007.06127)]

**InverseRenderNet: Learning Single Image Inverse Rendering.**<br>
*Ye Yu, William A. P. Smith.*<br>
CVPR 2019. [[PDF](http://openaccess.thecvf.com/content_CVPR_2019/html/Yu_InverseRenderNet_Learning_Single_Image_Inverse_Rendering_CVPR_2019_paper.html)] [[Github](https://github.com/YeeU/InverseRenderNet)] [[IIW Dataset](http://opensurfaces.cs.cornell.edu/publications/intrinsic/#download)] 

**Learning Inverse Rendering of Faces from Real-world Videos.**<br>
*Yuda Qiu, Zhangyang Xiong, Kai Han, Zhongyuan Wang, Zixiang Xiong, Xiaoguang Han.*<br>
arxiv, 2020. [[PDF](https://arxiv.org/abs/2003.12047)] [[Github](https://github.com/RudyQ/InverseFaceRender)]

## Neural Rerendering

**MetaNLR: Fast Training of Neural Lumigraph Representations using Meta Learning.**<br>
*Alexander W. Bergman, Petr Kellnhofer, and [Gordon Wetzstein](https://stanford.edu/~gordonwz/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.14942)] [[Project](https://www.computationalimaging.org/publications/metanlr/)] [[Video](https://youtu.be/5pBFwyUyW6o)]

**Hybrid Neural Fusion for Full-frame Video Stabilization.**<br>
*[Yu-Lun Liu](https://www.cmlab.csie.ntu.edu.tw/~nothinglo/), [Wei-Sheng Lai](https://www.wslai.net/), [Ming-Hsuan Yang](https://faculty.ucmerced.edu/mhyang/), [Yung-Yu Chuang](https://www.csie.ntu.edu.tw/~cyy/), [Jia-Bin Huang](https://filebox.ece.vt.edu/~jbhuang/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2102.06205)] [[Github](https://alex04072000.github.io/NeRViS/)]

**StyleUV: Diverse and High-fidelity UV Map Generative Model.**<br>
*Myunggi Lee, Wonwoong Cho, Moonheum Kim, David Inouye, Nojun Kwak.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2011.12893)]

**Neural Lumigraph Rendering.**<br>
*Petr Kellnhofer, Lars Jebe, Andrew Jones, Ryan Spicer, Kari Pulli, Gordon Wetzstein.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.11571)] [[Project](http://www.computationalimaging.org/publications/nlr/)] [[Data](https://drive.google.com/file/d/1BBpIfrqwZNYmG1TiFljlCnwsmL2OUxNT/view?usp=sharing)]

**Neural Re-Rendering of Humans from a Single Image.**<br>
*Kripasindhu Sarkar, Dushyant Mehta, Weipeng Xu, Vladislav Golyanik, Christian Theobalt.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2101.04104)]

**Neural Rerendering in the Wild.**<br>
*Moustafa Meshry, Dan B Goldman, Sameh Khamis, Hugues Hoppe, Rohit Pandey, Noah Snavely, Ricardo Martin-Brualla.*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1904.04290)]

**Revealing Scenes by Inverting Structure from Motion Reconstructions.**<br>
*Francesco Pittaluga, Sanjeev J. Koppal, Sing Bing Kang, Sudipta N. Sinha.*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1904.03303)]

## Differentiable Rendering

**Modular Primitives for High-Performance Differentiable Rendering.**<br>
*Samuli Laine, Janne Hellsten, Tero Karras, Yeongho Seol, Jaakko Lehtinen, Timo Aila.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2011.03277)] [[Github](https://github.com/NVlabs/nvdiffrast)]

**Neural Re-Rendering of Humans from a Single Image.**<br>
*Kripasindhu Sarkar, Dushyant Mehta, Weipeng Xu, Vladislav Golyanik, Christian Theobalt.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2101.04104)]

**Monocular Differentiable Rendering for Self-Supervised 3D Object Detection.**<br>
*Deniz Beker, Hiroharu Kato, Mihai Adrian Morariu, Takahiro Ando, Toru Matsuoka, Wadim Kehl, Adrien Gaidon.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2009.14524)]

## Volumetric Performance Capture (Free Viewpoint Video)

**HVH: Learning a Hybrid Neural Volumetric Representation for Dynamic Hair Performance Capture.**<br>
*Ziyan Wang, Giljoo Nam, Tuur Stuyck, Stephen Lombardi, Michael Zollhoefer, Jessica Hodgins, Christoph Lassner.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.06904)]

**Appearance Editing with Free-viewpoint Neural Rendering.**<br>
*Pulkit Gera, Aakash KT, Dhawal Sirikonda, Parikshit Sakurikar, P.J. Narayanan.*<br>
arxiv 2021. [[PDF](https://arxiv.org/pdf/2110.07674.pdf)]

**Geometry-Free View Synthesis: Transformers and No 3D Priors.**<br>
*Robin Rombach, Patrick Esser, Bjorn Ommer.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Rombach_Geometry-Free_View_Synthesis_Transformers_and_No_3D_Priors_ICCV_2021_paper.html)]

**iButter: Neural Interactive Bullet Time Generator for Human Free-viewpoint Rendering.**<br> 
*Liao Wang, Ziyu Wang, Pei Lin, Yuheng Jiang, Xin Suo, Minye Wu, Lan Xu, Jingyi Yu.*<br> 
ACM MM 2021. [[PDF](https://arxiv.org/abs/2108.05577)]

**ST-NeRF: Editable Free-viewpoint Video Using a Layered Neural Representation.**<br>
*Jiakai Zhang, Xinhang Liu, Xinyi Ye, Fuqiang Zhao, Yanshun Zhang, Minye Wu, Yingliang Zhang, Lan Xu, Jingyi Yu.*<br>
TOG 2021. [[PDF](https://arxiv.org/abs/2104.14786)]

**POSEFusion: Pose-guided Selective Fusion for Single-view Human Volumetric Capture.**<br>
*Zhe Li, Tao Yu, Zerong Zheng, Kaiwen Guo, Yebin Liu.*<br>
CVPR 2021 (oral). [[PDF](https://arxiv.org/abs/2103.15331)] [[Github](http://www.liuyebin.com/posefusion/posefusion.html)]

**NSVF: Neural Sparse Voxel Fields.**<br>
*[Lingjie Liu](https://lingjie0206.github.io/), Jiatao Gu, Kyaw Zaw Lin, Tat-Seng Chua, Christian Theobalt.*<br>
NeurIPS 2020. [[PDF](https://arxiv.org/abs/2007.11571)] [[Project](https://lingjie0206.github.io/papers/NSVF/)]

**Monocular Real-Time Volumetric Performance Capture.**<br>
*[Ruilong Li](https://www.liruilong.cn/), Yuliang Xiu, Shunsuke Saito, Zeng Huang, Kyle Olszewski, Hao Li.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2007.13988)]

**Volumetric Capture of Humans with a Single RGBD Camera via Semi-Parametric Learning.**<br>
*Rohit Pandey, Anastasia Tkach, Shuoran Yang, Pavel Pidlypenskyi, Jonathan Taylor, Ricardo Martin-Brualla, Andrea Tagliasacchi, George Papandreou, Philip Davidson, Cem Keskin, Shahram Izadi, Sean Fanello.*<br>
CVPR 2019. [[PDF](http://openaccess.thecvf.com/content_CVPR_2019/papers/Pandey_Volumetric_Capture_of_Humans_With_a_Single_RGBD_Camera_via_CVPR_2019_paper.pdf)]

**Neural Volumes: Learning Dynamic Renderable Volumes from Images.**<br>
*Stephen Lombardi, Tomas Simon, Jason Saragih, Gabriel Schwartz, Andreas Lehrmann, Yaser Sheikh.*<br>
TOG 2019. [[PDF](https://arxiv.org/abs/1906.07751)]

## Semantic Photo Synthesis and Manipulation

**StyleFlow: Attribute-conditioned Exploration of StyleGAN-Generated Images using Conditional Continuous Normalizing Flows.**<br>
*Rameen Abdal, Peihao Zhu, Niloy Mitra, Peter Wonka.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2008.02401)] [[Github](https://rameenabdal.github.io/StyleFlow)]

**Layered Neural Rendering for Retiming People in Video.**<br>
*Erika Lu, Forrester Cole, Tali Dekel, Weidi Xie, Andrew Zisserman, David Salesin, William T. Freeman, Michael Rubinstein.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2009.07833)] [[Project](https://retiming.github.io/)]

**Neural Hair Rendering.**<br>
*[Menglei Chai](mlchai.com), Jian Ren, Sergey Tulyakov.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2004.13297)]

**MichiGAN: Multi-Input-Conditioned Hair Image Generation for Portrait Editing.**<br>
*Zhentao Tan, Menglei Chai, Dongdong Chen, Jing Liao, Qi Chu, Lu Yuan, Sergey Tulyakov, Nenghai Yu.*<br>
TOG 2020. [[PDF](https://mlchai.com/files/tan2020michigan.pdf)]

**pix2pixHD: High-Resolution Image Synthesis and Semantic Manipulation with Conditional GANs.**<br>
*Ting-Chun Wang, Ming-Yu Liu, Jun-Yan Zhu, Andrew Tao, Jan Kautz, Bryan Catanzaro.*<br>
CVPR 2018. [[PDF](https://arxiv.org/abs/1711.11585)] [[Github](https://github.com/NVIDIA/pix2pixHD)]

**SPADE: Semantic Image Synthesis with Spatially-Adaptive Normalization.**</br>
*Taesung Park, Ming-Yu Liu, Ting-Chun Wang, Jun-Yan Zhu.*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1903.07291)] [[Github](https://github.com/NVlabs/SPADE)]

**Semantic Bottleneck Scene Generation.**<br>
*Samaneh Azadi, Michael Tschannen, Eric Tzeng, Sylvain Gelly, Trevor Darrell, Mario Lucic.*<br>
arxiv 2019. [[PDF](https://arxiv.org/abs/1911.11357)] [[Github](https://github.com/azadis/SB-GAN)]

**Local Class-Specific and Global Image-Level Generative Adversarial Networks for Semantic-Guided Scene Generation.**<br>
*[Hao Tang](http://disi.unitn.it/~hao.tang/), Dan Xu, Yan Yan, Philip H. S. Torr, [Nicu Sebe](https://scholar.google.com/citations?user=stFCYOAAAAAJ&hl=en).*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/1912.12215)] [[Github](https://github.com/Ha0Tang/LGGAN)]

**SelectionGAN: Multi-Channel Attention Selection GAN with Cascaded Semantic Guidance for Cross-View Image Translation.**<br>
*Hao Tang, Dan Xu, Nicu Sebe, Yanzhi Wang, Jason J. Corso, Yan Yan.*<br>
VPR 2019. [[PDF](https://arxiv.org/abs/1904.06807)] [[Github](https://github.com/Ha0Tang/SelectionGAN)]

## Texture and Surface Embedding or Mapping

**Transposer: Universal Texture Synthesis Using Feature Maps as Transposed Convolution Filter.**<br>
*Guilin Liu, Rohan Taori, Ting-Chun Wang, Zhiding Yu, Shiqiu Liu, Fitsum A. Reda, Karan Sapra, Andrew Tao, Bryan Catanzaro.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2007.07243)]

**Wasserstein Generative Models for Patch-based Texture Synthesis.**<br>
*Antoine Houdard, Arthur Leclaire, Nicolas Papadakis, Julien Rabin.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2007.03408)]

**GramGAN: Deep 3D Texture Synthesis From 2D Exemplars.**<br>
*Tiziano Portenier, Siavash Bigdeli, Orçun Göksel.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2006.16112)]

**IALS: Learning High-Fidelity Face Texture Completion without Complete Face Texture.**<br>
*Jongyoo Kim, Jiaolong Yang, Xin Tong.*<br>
ICCV 2021. [[PDF](https://arxiv.org/pdf/2105.12660.pdf)] [[Github](https://github.com/yxuhan/IALS)]

**Neural Surface Maps.**<br>
*Luca Morreale, Noam Aigerman, Vladimir Kim, Niloy J. Mitra.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.16942)] [[Github](http://geometry.cs.ucl.ac.uk/projects/2021/neuralmaps/)]

**NeuTex: Neural Texture Mapping for Volumetric Neural Rendering.**<br>
*Fanbo Xiang, Zexiang Xu, Miloš Hašan, Yannick Hold-Geoffroy, Kalyan Sunkavalli, Hao Su.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.00762)]

**Better Patch Stitching for Parametric Surface Reconstruction.**<br>
*Zhantao Deng, Jan Bednařík, Mathieu Salzmann, Pascal Fua.*<br>
3DV 2020. [[PDF](https://arxiv.org/abs/2010.07021)]

**Continuous Surface Embeddings.**<br>
*Natalia Neverova, David Novotny, Marc Szafraniec, Vasil Khalidov, Patrick Labatut, Andrea Vedaldi.*<br>
NerIPS 2020. [[PDF](https://arxiv.org/abs/2011.12438)]

**Deep Geometric Texture Synthesis.**<br>
*Amir Hertz, Rana Hanocka, Raja Giryes, Daniel Cohen-Or.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2007.00074)]

**Leveraging 2D Data to Learn Textured 3D Mesh Generation.**<br>
*Paul Henderson, Vagia Tsiminaki, Christoph H. Lampert.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2004.04180)]

**Articulation-aware Canonical Surface Mapping.**<br>
*Nilesh Kulkarni, Abhinav Gupta, David F. Fouhey, Shubham Tulsiani.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2004.00614)] [[Github](https://github.com/nileshkulkarni/acsm/)] [[Project](https://nileshkulkarni.github.io/acsm/)]

**UnrealText: Synthesizing Realistic Scene Text Images from the Unreal World.**<br>
*Shangbang Long, Cong Yao.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2003.10608)] [[Github](https://github.com/Jyouhou/UnrealText)]

**Adversarial Texture Optimization from RGB-D Scans.**<br>
*[Jingwei Huang](http://stanford.edu/~jingweih/), [Justus Thies](http://abhijitkundu.info/), [Angela Dai](https://www.3dunderstanding.org/), [Abhijit Kundu](https://justusthies.github.io/), [Chiyu Jiang](https://www.maxjiang.ml/), [Leonidas Guibas](https://geometry.stanford.edu/member/guibas/), [Matthias Nießner](http://www.niessnerlab.org/), [Thomas Funkhouser](https://www.cs.princeton.edu/~funk/).*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2003.08400)] [[Project](http://stanford.edu/~jingweih/papers/advtex/)] [[Github](https://github.com/hjwdzh/AdversarialTexture)] [[pyRender](https://github.com/hjwdzh/pyRender)]

**Learning Elementary Structures For 3D Shape Generation And Matching.**<br>
*Theo Deprelle, Thibault Groueix, Matthew Fisher, Vladimir G. Kim, Bryan C. Russell, Mathieu Aubry.*<br>
TOG 2019. [[PDF](https://arxiv.org/abs/1908.04725)] [[Project](http://imagine.enpc.fr/~deprellt/atlasnet2/)] [[Github](https://github.com/TheoDEPRELLE/AtlasNetV2)]

**Learning to Generate Textures on Meshes.**<br>
*Amit Raj, [Cusuh Ham](https://cusuh.github.io/), Connelly Barnes, Vladimir Kim, Jingwan Lu, James Hays.*<br>
CVPR 2019 Workshops on [Deep Generative Models for 3D Understanding](https://sites.google.com/view/3d-widget/) (Best Paper). [[PDF](http://openaccess.thecvf.com/content_cvprw_20/papers/3D-WidDGET/Amit_Raj_Learning_to_Generate_Textures_on_3D_Meshes_CVPRW_2019_paper.pdf)]

**CSM: Canonical Surface Mapping via Geometric Cycle Consistency.**<br>
*Nilesh Kulkarni, Abhinav Gupta, Shubham Tulsiani.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1907.10043)] [[Github](https://nileshkulkarni.github.io/csm/)] [[Project](https://nileshkulkarni.github.io/csm/)]

**Texture Fields: Learning Texture Representations in Function Space.**<br>
*Michael Oechsle, Lars Mescheder, Michael Niemeyer, Thilo Strauss, Andreas Geiger.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1905.07259)]

**Learning Category-Specific Mesh Reconstruction from Image Collections.**<br>
*Angjoo Kanazawa, Shubham Tulsiani Alexei A. Efros, Jitendra Malik.*<br>
ECCV 2018. [[Github](akanazawa.github.io/cmr/)] [[Project](https://github.com/akanazawa/cmr)]
 
**AtlasNet: A Papier-Mache Approach to Learning 3D Surface Generation.**<br>
*Thibault Groueix, Matthew Fisher, Vladimir Kim, Bryan Russell, Mathieu Aubry.*<br>
CVPR 2018. [[PDF](https://hal.inria.fr/hal-01718933/file/1802.05384.pdf)] [[Project](http://imagine.enpc.fr/~groueixt/atlasnet/)] [[Github](https://github.com/ThibaultGROUEIX/AtlasNet)]

**Texture Mapping for 3D Reconstruction with RGB-D Sensor.**<br>
*Yanping Fu, [Qingan Yan](https://yanqingan.github.io/), Long Yang, Jie Liao, [Chunxia Xiao](http://graphvision.whu.edu.cn/).*<br>
CVPR 2018. [[PDF](https://yanqingan.github.io/docs/cvpr18_texture.pdf)] [[thecvf](http://openaccess.thecvf.com/content_cvpr_2018/papers/Fu_Texture_Mapping_for_CVPR_2018_paper.pdf)] [[Code on Github](https://github.com/fdp0525/G2LTex)]

**Let There Be Color! - Large-Scale Texturing of 3D Reconstructions.**<br>
*Waechter, Michael and Moehrle, Nils and Goesele, Michael.*<br>
ECCV 2018. [[PDF](https://www.gcc.tu-darmstadt.de/media/gcc/papers/Waechter-2014-LTB.pdf)] [[Project](http://www.gcc.tu-darmstadt.de/home/proj/texrecon/)] [[Github](https://github.com/nmoehrle/mvs-texturing)] [[rayint](https://github.com/nmoehrle/rayint)] [[Eigen](http://eigen.tuxfamily.org)] [[Multi-View Environment](http://www.gcc.tu-darmstadt.de/home/proj/mve)] [[mapMAP](http://www.gcc.tu-darmstadt.de/home/proj/mapmap)]

**Unsupervised Texture Transfer from Images to Model Collections.**<br>
*[Tuanfeng Yand Wang](http://geometry.cs.ucl.ac.uk/tuanfeng/), [Hao Su](http://ai.ucsd.edu/~haosu/), Qixing Huang, Jingwei Huang, Leonidas J. Guibas, [Niloy J. Mitra](http://www0.cs.ucl.ac.uk/staff/n.mitra/index.html).*<br>
TOG 2016. [[PDF](http://ai.ucsd.edu/~haosu/papers/siga16.texture_transfer_small.pdf)] [[Project](http://geometry.cs.ucl.ac.uk/projects/2016/texture_transfer/)] [[Data](http://geometry.cs.ucl.ac.uk/tuanfeng/texturetransfer/texture_transfer_code_and_data.zip)]

## Implicit Neural Scene Representation and Rendering

[[Awesome Neural Radiance Fields](https://github.com/yenchenlin/awesome-NeRF)]

[[NeRF Explosion 2020](https://dellaert.github.io/NeRF/)]

**[3D Scene Generation.](https://3dscenegen.github.io/)**<br>
*[Angel X. Chang](https://angelxuanchang.github.io/), [Daniel Ritchie](https://dritchie.github.io/), [Qixing Huang](https://www.cs.utexas.edu/~huangqx/), [Manolis Savva](http://msavva.github.io/).*<br>
CVPR 2019 Workshop.

**NeRF-Supervision: Learning Dense Object Descriptors from Neural Radiance Fields.**<br>
*[Lin Yen-Chen](https://yenchenlin.me/), [Pete Florence](http://www.peteflorence.com/), [Jonathan T. Barron](https://jonbarron.info/), [Tsung-Yi Lin](https://tsungyilin.info/), [Alberto Rodriguez](https://meche.mit.edu/people/faculty/ALBERTOR@MIT.EDU), [Phillip Isola](http://web.mit.edu/phillipi/).*<br>
ICRA 2022. [[PDF](https://arxiv.org/abs/2203.01913)] [[Project](https://yenchenlin.me/nerf-supervision/)] [[Github](https://github.com/yenchenlin/nerf-supervision-public)]

**NeuroFluid: Fluid Dynamics Grounding with Particle-Driven Neural Radiance Fields.**<br>
*Shanyan Guan, Huayu Deng, Yunbo Wang, Xiaokang Yang.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2203.01762)]

**Pix2NeRF: Unsupervised Conditional π-GAN for Single Image to Neural Radiance Fields Translation.**<br>
*Shengqu Cai, Anton Obukhov, Dengxin Dai, Luc Van Gool.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.13162)]

**NeuralFusion: Neural Volumetric Rendering under Human-object Interactions.**<br>
*Yuheng Jiang, Suyi Jiang, Guoxing Sun, Zhuo Su, Kaiwen Guo, Minye Wu, Jingyi Yu, Lan Xu.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.12825)]

**Learning Smooth Neural Functions via Lipschitz Regularization.**<br>
*Hsueh-Ti Derek Liu, Francis Williams, Alec Jacobson, Sanja Fidler, Or Litany.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.08345)]

**Fourier PlenOctrees for Dynamic Radiance Field Rendering in Real-time.**<br>
*Liao Wang, Jiakai Zhang, Xinhang Liu, Fuqiang Zhao, Yanshun Zhang, Yingliang Zhang, Minye Wu, Lan Xu, Jingyi Yu.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.08614)]

**NeuVV: Neural Volumetric Videos with Immersive Rendering and Editing.**<br>
*Jiakai Zhang, Liao Wang, Xinhang Liu, Fuqiang Zhao, Minzhang Li, Haizhao Dai, Boyuan Zhang, Wei Yang, Lan Xu, Jingyi Yu.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.06088)]

**Artemis: Articulated Neural Pets with Appearance and Motion synthesis.**<br>
*Haimin Luo, Teng Xu, Yuheng Jiang, Chenglin Zhou, QIwei Qiu, Yingliang Zhang, Wei Yang, Lan Xu, Jingyi Yu.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.05628)]

**HumanNeRF: Free-viewpoint Rendering of Moving People from Monocular Video.**<br>
*Chung-Yi Weng, Brian Curless, Pratul Srinivasan,Jonathan T. Barron, Ira Kemelmacher-Shlizerman.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2201.04127)] [[Project](https://grail.cs.washington.edu/projects/humannerf/)]

**Block-NeRF: Scalable Large Scene Neural View Synthesis.**<br>
*Matthew Tancik, Vincent Casser, Xinchen Yan, Sabeek Pradhan, Ben Mildenhall, Pratul P. Srinivasan, Jonathan T. Barron, Henrik Kretzschmar.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2202.05263)] [[Project](https://waymo.com/research/block-nerf/)]

**NeAT: Neural Adaptive Tomography.**<br>
*Darius Rückert, Yuanhao Wang, Rui Li, Ramzi Idoughi, Wolfgang Heidrich.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.02171)]

**SPAGHETTI: Editing Implicit Shapes Through Part Aware Generation.**<br>
*Amir Hertz, Or Perel, Raja Giryes, Olga Sorkine-Hornung, Daniel Cohen-Or.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2201.13168)] [[Github](https://github.com/amirhertz/spaghetti)]

**CLA-NeRF: Category-Level Articulated Neural Radiance Field.**<br> 
*Wei-Cheng Tseng, Hung-Ju Liao, Yen-Chen Lin, Min Sun.*<br> 
ICRA 2022. [[PDF](https://arxiv.org/abs/2202.00181)]

**Differentiable Gradient Sampling for Learning Implicit 3D Scene Reconstructions from a Single Image.**<br> 
*Shizhan Zhu, Sayna Ebrahimi, Angjoo Kanazawa, Trevor Darrell.*<br>
ICLR 2022. [[PDF](https://openreview.net/forum?id=U8pbd00cCWB)]

**Unsupervised Discovery of Object Radiance Fields.**<br>
*Hong-Xing Yu, Leonidas Guibas, Jiajun Wu.*<br>
ICLR 2022. [[PDF](https://openreview.net/forum?id=rwE8SshAlxw)]

**CoordX: Accelerating Implicit Neural Representation with a Split MLP Architecture.**<br> 
*Ruofan Liang, Hongyi Sun, Nandita Vijaykumar.*<br>
ICLR 2022. [[PDF](https://openreview.net/forum?id=oAy7yPmdNz)]

**Point-NeRF: Point-based Neural Radiance Fields.**<br>
*Qiangeng Xu, Zexiang Xu, Julien Philip, Sai Bi, Zhixin Shu, Kalyan Sunkavalli, Ulrich Neumann.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2201.08845)] 

**ImpliCity: City Modeling from Satellite Images with Deep Implicit Occupancy Fields.**<br>
*Corinne Stucker, Bingxin Ke, Yuanwen Yue, Shengyu Huang, [Iro Armeni](https://ir0.github.io/), Konrad Schindler.*<br>
ISPRS Congress 2022. [[PDF](https://arxiv.org/abs/2201.09968)] 

**Instant Neural Graphics Primitives with a Multiresolution Hash Encoding.**<br>
*[Thomas Müller]()https://tom94.net/, [Alex Evans](https://research.nvidia.com/person/alex-evans), [Christoph Schied](https://research.nvidia.com/person/christoph-schied), [Alexander Keller](https://research.nvidia.com/person/alex-keller).*<br>
arxiv 2021. [[PDF](https://nvlabs.github.io/instant-ngp/assets/mueller2022instant.pdf)] [[Project](https://nvlabs.github.io/instant-ngp)][[Github](https://github.com/NVlabs/instant-ngp)]

**NeROIC: Neural Rendering of Objects from Online Image Collections.**<br>
*[Zhengfei Kuang](https://zhengfeikuang.com/), Kyle Olszewski, Menglei Chai, Zeng Huang, Panos Achlioptas, Sergey Tulyakov.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2201.02533)] [[Github](https://formyfamily.github.io/NeROIC/)]

**DFA-NeRF: Personalized Talking Head Generation via Disentangled Face Attributes Neural Rendering.**<br>
*Shunyu Yao, RuiZhe Zhong, Yichao Yan, Guangtao Zhai, Xiaokang Yang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2201.00791)]

**InfoNeRF: Ray Entropy Minimization for Few-Shot Neural Volume Rendering.**<br>
*[Mijeong Kim](https://mjmjeong.github.io/), [Seonguk Seo](https://seoseong.uk/), [Bohyung Han](https://cv.snu.ac.kr/index.php/~bhhan/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.15399)] [[Project](https://cv.snu.ac.kr/research/InfoNeRF/)] [[Github](https://github.com/mjmjeong/InfoNeRF)]

**3D-aware Image Synthesis via Learning Structural and Textural Representations.**<br>
*Yinghao Xu, Sida Peng, Ceyuan Yang, Yujun Shen, Bolei Zhou.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.10759)] [[Project](https://genforce.github.io/volumegan/)] [[Github](https://github.com/genforce/VolumeGAN)]

**Improving Neural Implicit Surfaces Geometry with Patch Warping.**<br>
*[François Darmon](http://imagine.enpc.fr/~darmonf/), Bénédicte Bascle, Jean-Clément Devaux, Pascal Monasse, Mathieu Aubry.*<br>
arxiv 2021. [[PDF](https://arxiv.org/pdf/2112.09648.pdf)] [[Project](http://imagine.enpc.fr/~darmonf/NeuralWarp/)] [[Github](https://github.com/fdarmon/NeuralWarp)]

**GRAM: Generative Radiance Manifolds for 3D-Aware Image Generation.**<br>
*Yu Deng, Jiaolong Yang, Jianfeng Xiang, Xin Tong.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.08867)] [[Project](https://yudeng.github.io/GRAM/)] [[Github](https://yudeng.github.io/GRAM/)]

**UNIST: Unpaired Neural Implicit Shape Translation Network.**<br>
*Qimin Chen, Johannes Merz, Aditya Sanghi, Hooman Shayani, Ali Mahdavi-Amiri, Hao Zhang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2110.00966)] [[Project](https://qiminchen.github.io/unist/)]

**HeadNeRF: A Real-time NeRF-based Parametric Head Model.**<br>
*[Yang Hong](https://hy1995.top/), Peng Bo, Haiyao Xiao, Ligang Liu, Juyong Zhang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05637)] [[Project](https://crishy1995.github.io/HeadNeRF-Project/)]

**PERF: Performant, Explicit Radiance Fields.**<br>
*Sverker Rasmuson, Erik Sintorn, Ulf Assarsson.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05598)] 

**CityNeRF: Building NeRF at City Scale.**<br>
*Yuanbo Xiangli, Linning Xu, Xingang Pan, Nanxuan Zhao, Anyi Rao, Christian Theobalt, Bo Dai, Dahua Lin.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05504)] [[Project](https://city-super.github.io/citynerf)]

**CLIP-NeRF: Text-and-Image Driven Manipulation of Neural Radiance Fields.**<br>
*Can Wang, Menglei Chai, Mingming He, Dongdong Chen, Jing Liao.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05139)]

**Neural Descriptor Fields: SE(3)-Equivariant Object Representations for Manipulation.**<br>
*Anthony Simeonov, Yilun Du, Andrea Tagliasacchi, Joshua B. Tenenbaum, Alberto Rodriguez, Pulkit Agrawal, Vincent Sitzmann.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05124)] [[Project](https://yilundu.github.io/ndf/)]

**Plenoxels: Radiance Fields without Neural Networks.**<br>
*Alex Yu, Sara Fridovich-Keil, Matthew Tancik, Qinhong Chen, Benjamin Recht, Angjoo Kanazawa.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05131)] [[Project](https://alexyu.net/plenoxels)]

**DD-NeRF: Double-Diffusion Neural Radiance Field as a Generalizable Implicit Body Representation.**<br>
*Guangming Yao, Hongzhi Wu, Yi Yuan, Kun Zhou.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.12390)]

**Neural Radiance Fields for Outdoor Scene Relighting.**<br>
*Viktor Rudnev, Mohamed Elgharib, William Smith, Lingjie Liu, Vladislav Golyanik, Christian Theobalt.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05140)] [[Project](https://4dqv.mpi-inf.mpg.de/NeRF-OSR/)]

**Geometry-Guided Progressive NeRF for Generalizable and Efficient Neural Human Rendering.**<br>
*Mingfei Chen, Jianfeng Zhang, Xiangyu Xu, Lijuan Liu, Jiashi Feng, Shuicheng Yan.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.04312)]

**Dense Depth Priors for Neural Radiance Fields from Sparse Input Views.**<br>
*Barbara Roessle, Jonathan T. Barron, Ben Mildenhall, Pratul P. Srinivasan, Matthias Nießner.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2112.03288)] [[Project](https://youtu.be/zzkvvdcvksc)]

**CG-NeRF: Conditional Generative Neural Radiance Fields.**<br>
*Kyungmin Jo, Gyumin Shim, Sanghun Jung, Soyoung Yang, Jaegul Choo.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.03517)]

**Ref-NeRF: Structured View-Dependent Appearance for Neural Radiance Fields.**<br>
*Dor Verbin, Peter Hedman, Ben Mildenhall, Todd Zickler, Jonathan T. Barron, Pratul P. Srinivasan.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2112.03907)] [[Project](https://dorverbin.github.io/refnerf/)]

**MoFaNeRF: Morphable Facial Neural Radiance Field.**<br>
*Yiyu Zhuang, Hao Zhu, Xusen Sun, Xun Cao.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.02308)]

**HumanNeRF: Generalizable Neural Human Radiance Field from Sparse Inputs.**<br>
*Fuqiang Zhao, Wei Yang, Jiakai Zhang, Pei Lin, Yingliang Zhang, Jingyi Yu, Lan Xu.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.02789)]

**CoNeRF: Controllable Neural Radiance Fields.**<br>
*Kacper Kania, Kwang Moo Yi, Marek Kowalski, Tomasz Trzciński, Andrea Taliasacchi.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.01983)] [[Project](https://conerf.github.io/)]

**NeSF: Neural Shading Field for Image Harmonization.**<br>
*Zhongyun Hu, Ntumba Elie Nsampi, Xue Wang, Qing Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.01314)]

**Learning Neural Light Fields with Ray-Space Embedding Networks.**<br>
*Benjamin Attal, Jia-Bin Huang, Michael Zollhoefer, Johannes Kopf, Changil Kim.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.01523)] [[Project](https://neural-light-fields.github.io/)]

**Zero-Shot Text-Guided Object Generation with Dream Fields.**<br>
*Ajay Jain, Ben Mildenhall, Jonathan T. Barron, Pieter Abbeel, Ben Poole.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.01455)] [[Project](https://ajayj.com/dreamfields)]

**RegNeRF: Regularizing Neural Radiance Fields for View Synthesis from Sparse Inputs.**<br>
*Michael Niemeyer, Jonathan T. Barron, Ben Mildenhall, Mehdi S. M. Sajjadi, Andreas Geiger, Noha Radwan.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2112.00724)] [[Project](https://m-niemeyer.github.io/regnerf/index.html)]

**NeRFReN: Neural Radiance Fields with Reflections.**<br>
*Yuan-Chen Guo, Di Kang, Linchao Bao, Yu He, Song-Hai Zhang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.15234)] [[Project](https://bennyguo.github.io/nerfren/]

**Hallucinated Neural Radiance Fields in the Wild.**<br>
*Xingyu Chen, Qi Zhang, Xiaoyu Li, Yue Chen, Feng Ying, Xuan Wang, Jue Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.15246)] 

**FENeRF: Face Editing in Neural Radiance Fields.**<br>
*Jingxiang Sun, Xuan Wang, Yong Zhang, Xiaoyu Li, Qi Zhang, Yebin Liu, Jue Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.15490)] 

**NeuSample: Neural Sample Field for Efficient View Synthesis.**<br>
*Jiemin Fang, Lingxi Xie, Xinggang Wang, Xiaopeng Zhang, Wenyu Liu, Qi Tian.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.15552)] [[Project](https://jaminfong.cn/neusample/]

**Learning Continuous Environment Fields via Implicit Functions.**<br>
*Xueting Li, Shalini De Mello, Xiaolong Wang, Ming-Hsuan Yang, Jan Kautz, Sifei Liu.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.13997)]

**HDR-NeRF: High Dynamic Range Neural Radiance Fields.**<br>
*Xin Huang, Qi Zhang, Feng Ying, Hongdong Li, Xuan Wang, Qing Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.14451)] [[Project](https://shsf0817.github.io/hdr-nerf/]

**Deblur-NeRF: Neural Radiance Fields from Blurry Images.**<br>
*Li Ma, Xiaoyu Li, Jing Liao, Qi Zhang, Xuan Wang, Jue Wang, Pedro V. Sander.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.14292)]

**Urban Radiance Fields.**<br>
*[Konstantinos Rematas](http://www.krematas.com/), Andrew Liu, Pratul P. Srinivasan, Jonathan T. Barron, Andrea Tagliasacchi, Thomas Funkhouser, Vittorio Ferrari.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2111.14643)] [[Project](https://urban-radiance-fields.github.io/)]

**NeRF in the Dark: High Dynamic Range View Synthesis from Noisy Raw Images.**<br>
*[Ben Mildenhall](https://bmild.github.io/), [Peter Hedman](https://www.phogzone.com/), [Ricardo Martin-Brualla](http://ricardomartinbrualla.com/), [Pratul Srinivasan](https://pratulsrinivasan.github.io/), [Jonathan T. Barron](https://jonbarron.info/).*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2111.13679)] [[Project](https://bmild.github.io/rawnerf/index.html)]

**Mip-NeRF 360: Unbounded Anti-Aliased Neural Radiance Fields.**<br>
*Jonathan T. Barron, Ben Mildenhall, Dor Verbin, Pratul P. Srinivasan, Peter Hedman.*<br>
CVPR 2022. [[PDF](https://arxiv.org/abs/2111.12077)] 

**Direct Voxel Grid Optimization: Super-fast Convergence for Radiance Fields Reconstruction.**<br>
*Cheng Sun, Min Sun, Hwann-Tzong Chen.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.11215)] [[Github](https://github.com/sunset1995/DirectVoxGO)]

**LOLNeRF: Learn from One Look.**<br>
*Daniel Rebain, Mark Matthews, Kwang Moo Yi, Dmitry Lagun, Andrea Tagliasacchi.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2111.09996)]

**Learning Neural Transmittance for Efficient Rendering of Reflectance Fields.**<br>
*Mohammad Shafiei, Sai Bi, Zhengqin Li, Aidas Liaudanskas, Rodrigo Ortiz-Cayon, Ravi Ramamoorthi.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2110.13272)]

**CIPS-3D: A 3D-Aware Generator of GANs Based on Conditionally-Independent Pixel Synthesis.**<br>
*Peng Zhou, Lingxi Xie, Bingbing Ni, Qi Tian.*<br>
arxiv 2021. [[PDF](https://arxiv.org/pdf/2110.09788.pdf)] [[Github](https://github.com/PeterouZh/CIPS-3D)]

**Seeing Implicit Neural Representations as Fourier Series.**<br>
*Nuri Benbarka, Timon Höfer, Hamd ul-moqeet Riaz, Andreas Zell.*<br>
arxiv 2021. [[PDF](https://arxiv.org/pdf/2109.00249.pdf)]

**Geometry-Consistent Neural Shape Representation with Implicit Displacement Fields.**<br>
*[Wang Yifan](https://yifita.github.io/), Lukas Rahmann, [Olga Sorkine-Hornung](https://igl.ethz.ch/people/sorkine/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.05187)] [[Project](https://yifita.github.io/publication/idf/)] [[Github](https://github.com/yifita/idf)]

**StyleNeRF: A Style-based 3D-Aware Generator for High-resolution Image Synthesis.**<br>
*Jiatao Gu, Lingjie Liu, Peng Wang, Christian Theobalt.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2110.08985)] [[Project](http://jiataogu.me/style_nerf/)]

**CodeNeRF: Disentangled Neural Radiance Fields for Object Categories.**<br>
*Wonbong Jang, Lourdes Agapito.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2109.01750)] [[Project](https://sites.google.com/view/wbjang/home/codenerf)] [[Github](https://github.com/wayne1123/code-nerf)]

**Neural Volume Rendering: NeRF And Beyond.**<br>
*[Frank Dellaert](https://dellaert.github.io/), [Lin Yen-Chen](https://yenchenlin.me/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2101.05204)]

**FLAME-in-NeRF: Neural control of Radiance Fields for Free View Face Animation.**<br>
*[ShahRukh Athar](http://shahrukhathar.github.io/about/), [Zhixin Shu](https://zhixinshu.github.io/), [Dimitris Samaras](http://www3.cs.stonybrook.edu/~samaras/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2108.04913)] [[Project](http://shahrukhathar.github.io/2021/08/12/FLAMEinNeRF.html)]

**Unsupervised Discovery of Object Radiance Fields.**<br>
*[Hong-Xing Yu](https://kovenyu.com/), [Leonidas J. Guibas](https://geometry.stanford.edu/member/guibas/), [Jiajun Wu](https://jiajunwu.com/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2107.07905)] [[Github](https://github.com/KovenYu/uORF)] [[Project](https://kovenyu.com/uorf/)]

**Depth-supervised NeRF: Fewer Views and Faster Training for Free.**<br>
*[Kangle Deng](https://andrewhliu.github.io/), [Andrew Liu](https://andrewhliu.github.io/), [Jun-Yan Zhu](https://www.cs.cmu.edu/~junyanz/), [Deva Ramanan](https://www.cs.cmu.edu/~deva/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2107.02791)] [[Project](https://www.cs.cmu.edu/~dsnerf/)] [[Github](https://github.com/dunbar12138/DSNeRF)]

**FiG-NeRF: Figure Ground Neural Radiance Fields for 3D Object Category Modelling.**<br> 
*[Christopher Xie](https://chrisdxie.github.io/), [Keunhong Park](https://keunhong.com/), [Ricardo Martin-Brualla](http://www.ricardomartinbrualla.com/), [Matthew Brown](http://matthewalunbrown.com/).*<br> 
arxiv 2021. [[PDF](https://arxiv.org/pdf/2104.08418.pdf)] [[Project](https://fig-nerf.github.io/)]

**Volume Rendering of Neural Implicit Surfaces.**<br> 
*Lior Yariv, Jiatao Gu, Yoni Kasten, Yaron Lipman.*<br> 
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.12052)]

**NeRF in Detail (NeRF-ID): Learning to Sample for View Synthesis.**<br> 
*Relja Arandjelović, Andrew Zisserman.*<br> 
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.05264)]

**Deep Medial Fields.**<br>
*Daniel Rebain, Ke Li, Vincent Sitzmann, Soroosh Yazdani, Kwang Moo Yi, Andrea Tagliasacchi.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.03804)]

**DoubleField: Bridging the Neural Surface and Radiance Fields for High-fidelity Human Rendering.**<br>
*Ruizhi Shao, Hongwen Zhang, He Zhang, Yanpei Cao, Tao Yu, Yebin Liu.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.03798)] [[Project](http://www.liuyebin.com/dbfield/dbfield.html)]

**SIMONe: View-Invariant, Temporally-Abstracted Object Representations via Unsupervised Video Decomposition.**<br>
*Rishabh Kabra, Daniel Zoran, Goker Erdogan, Loic Matthey, Antonia Creswell, Matthew Botvinick, Alexander Lerc.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.03849)]

**Light Field Networks (LFNS): Neural Scene Representations with Single-Evaluation Rendering.**<br>
*Vincent Sitzmann, Semon Rezchikov, William T. Freeman, Joshua B. Tenenbaum, Fredo Durand.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2106.02634)] [[Project](https://vsitzmann.github.io/lfns/)]

**Recursive-NeRF: An Efficient and Dynamically Growing NeRF.**<br>
*Guo-Wei Yang, Wen-Yang Zhou, Hao-Yang Peng, Dun Liang, Tai-Jiang Mu, Shi-Min Hu.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2105.09103)] [[Github](https://github.com/Gword/Recursive-NeRF)]

**NeRF--: Neural Radiance Fields Without Known Camera Parameters.**<br>
*Zirui Wang, Shangzhe Wu, [Weidi Xie](https://weidixie.github.io/weidi-personal-webpage/), [Min Chen](https://sites.google.com/site/drminchen/home), [Victor Adrian Prisacariu](https://eng.ox.ac.uk/people/victor-prisacariu/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2102.07064)] [[Project](http://nerfmm.active.vision/)] [[Github](https://github.com/ActiveVisionLab/nerfmm)]

**Non-Rigid Neural Radiance Fields: Reconstruction and Novel View Synthesis of a Deforming Scene from Monocular Video.**<br>
*Edgar Tretschk, Ayush Tewari, Vladislav Golyanik, Michael Zollhöfer, Christoph Lassner, Christian Theobalt.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.12247)] [[Project](https://gvv.mpi-inf.mpg.de/projects/nonrigid_nerf/)] [[Github](https://github.com/facebookresearch/nonrigid_nerf)]

**Learning Compositional Radiance Fields of Dynamic Human Heads.**<br>
*Ziyan Wang, Timur Bagautdinov, Stephen Lombardi, Tomas Simon, Jason Saragih, Jessica Hodgins, Michael Zollhöfer.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.09955)]

**OSF: Object-Centric Neural Scene Rendering.**<br>
*[Michelle Guo](https://shellguo.com/), [Alireza Fathi](https://www.alirezafathi.org/), [Jiajun Wu](https://jiajunwu.com/), [Thomas Funkhouser](https://www.cs.princeton.edu/~funk/).*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.08503)] [[Project](https://www.shellguo.com/osf)]

**Portrait Neural Radiance Fields from a Single Image.**<br>
*[Chen Gao](http://chengao.vision/), [Yichang Shih](https://people.csail.mit.edu/yichangshih/), [Wei-Sheng Lai](https://www.wslai.net/), [Chia-Kai Liang](http://chiakailiang.org/), [Jia-Bin Huang](https://filebox.ece.vt.edu/~jbhuang/).*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.05903)] [[Project](https://portrait-nerf.github.io/)]

**A-NeRF: Articulated Neural Radiance Fields for Learning Human Shape, Appearance, and Pose.**<br>
*[Shih-Yang Su](https://lemonatsu.github.io/), [Frank Yu](https://yu-frank.github.io/), [Michael Zollhoefer](https://zollhoefer.com/), [Helge Rhodin](http://helge.rhodin.de/).*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2102.06199)] [[Project](https://lemonatsu.github.io/ANeRF-Surface-free-Pose-Refinement/)]

**H-NeRF: Neural Radiance Fields for Rendering and Temporal Reconstruction of Humans in Motion .**<br>
*[Hongyi Xu](http://www-scf.usc.edu/~hongyixu/), Thiemo Alldieck, Cristian Sminchisescu.*<br>
NeurIPS 2021. [[PDF](https://papers.nips.cc/paper/2021/hash/7d62a275027741d98073d42b8f735c68-Abstract.html)]

**A Shading-Guided Generative Implicit Model for Shape-Accurate 3D-Aware Image Synthesis.**<br>
*Xingang Pan, Xudong Xu, Chen Change Loy, Christian Theobalt, Bo Dai.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2110.15678)]

**Neural Human Performer: Learning Generalizable Radiance Fields for Human Performance Rendering.**<br>
*Youngjoong Kwon, Dahun Kim, Duygu Ceylan, Henry Fuchs.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2109.07448)] [[Project](https://youngjoongunc.github.io/nhp/)] [[Github](https://github.com/YoungJoongUNC/Neural_Human_Performer)]

**OctField: Hierarchical Implicit Functions for 3D Modeling.**<br>
*Jia-Heng Tang, Weikai Chen, Jie Yang, Bo Wang, Songrun Liu, Bo Yang, Lin Gao.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2111.01067)]

**Neural Relightable Participating Media Rendering.**<br>
*Quan Zheng, Gurprit Singh, Hans-Peter Seidel.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2110.12993)]

**NeuS: Learning Neural Implicit Surfaces by Volume Rendering for Multi-view Reconstruction.**<br>
*Peng Wang, Lingjie Liu, Yuan Liu, Christian Theobalt, Taku Komura, Wenping Wang.*<br>
NeurIPS 2021. [[PDF](https://papers.nips.cc/paper/2021/hash/e41e164f7485ec4a28741a2d0ea41c74-Abstract.html)]

**NeRV: Neural Representations for Videos.**<br>
*Hao Chen, Bo He, Hanyu Wang, Yixuan Ren, Ser-Nam Lim, Abhinav Shrivastava.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2110.13903)] [[Github](https://github.com/haochen-rye/NeRV.git)]

**NeRS: Neural Reflectance Surfaces for Sparse-view 3D Reconstruction in the Wild.**<br>
*[Jason Y. Zhang](https://jasonyzhang.com/), [Gengshan Yang](https://gengshan-y.github.io/), [Shubham Tulsiani](https://shubhtuls.github.io/), [Deva Ramanan](https://www.cs.cmu.edu/~deva/).*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2110.07604)] [[Project](https://jasonyzhang.com/ners/)] [[Github](https://github.com/jasonyzhang/ners)] [[Data](https://jasonyzhang.com/ners/meshes)]

**TöRF: Time-of-Flight Radiance Fields for Dynamic Scene View Synthesis.**<br>
*Benjamin Attal, Eliot Laidlaw, Aaron Gokaslan, Changil Kim, Christian Richardt, James Tompkin, Matthew O'Toole.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2109.15271)] [[Github](https://imaging.cs.cmu.edu/torf/)]

**Non-line-of-Sight Imaging via Neural Transient Fields.**<br>
*Siyuan Shen, Zi Wang, Ping Liu, Zhengqing Pan, Ruiqian Li, Tian Gao, Shiying Li, [Jingyi Yu](http://www.yu-jingyi.com/cv/).*<br>
TPAMI 2021. [[PDF](https://arxiv.org/abs/2101.00373)]

**NeRFactor: Neural Factorization of Shape and Reflectance Under an Unknown Illumination.**<br>
*[Xiuming Zhang](http://people.csail.mit.edu/xiuming/), [Pratul P. Srinivasan](https://pratulsrinivasan.github.io/), [Boyang Deng](https://boyangdeng.com/), [Paul Debevec](http://www.pauldebevec.com/), [William T. Freeman](http://billf.mit.edu/), [Jonathan T. Barron](https://jonbarron.info/).*<br>
TOG 2021. [[PDF](https://arxiv.org/abs/2106.01970)] [[Project](http://people.csail.mit.edu/xiuming/projects/nerfactor/)] [[Github](https://github.com/google/nerfactor)]

**Mixture of Volumetric Primitives for Efficient Neural Rendering.**<br>
*Stephen Lombardi, Tomas Simon, Gabriel Schwartz, Michael Zollhoefer, Yaser Sheikh, Jason Saragih.*<br>
TOG 2021. [[PDF](https://arxiv.org/abs/2103.01954)]

**HyperNeRF: A Higher-Dimensional Representation for Topologically Varying Neural Radiance Fields.**<br>
*[Keunhong Park](https://keunhong.com/), [Utkarsh Sinha](https://utkarshsinha.com/), [Peter Hedman](https://phogzone.com/), [Jonathan T. Barron](https://jonbarron.info/), [Sofien Bouaziz](http://sofienbouaziz.com/), [Dan B Goldman](https://www.danbgoldman.com/home/), [Ricardo Martin-Brualla](http://ricardomartinbrualla.com/), [Steven M. Seitz](https://www.smseitz.com/).*<br>
TOG 2021. [[PDF](https://arxiv.org/abs/2106.13228)] [[Project](https://hypernerf.github.io/)]

**GRF: Learning a General Radiance Field for 3D Representation and Rendering.**<br>
*Alex Trevithick, Bo Yang.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Trevithick_GRF_Learning_a_General_Radiance_Field_for_3D_Representation_and_ICCV_2021_paper.html)]

**FastNeRF: High-Fidelity Neural Rendering at 200FPS.**<br>
*Stephan J. Garbin, Marek Kowalski, Matthew Johnson, Jamie Shotton, Julien Valentin.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.10380)]

**Animatable Neural Radiance Fields for Modeling Dynamic Human Bodies.**<br>
*Sida Peng, Junting Dong, Qianqian Wang, Shangzhan Zhang, Qing Shuai, Xiaowei Zhou, Hujun Bao.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Peng_Animatable_Neural_Radiance_Fields_for_Modeling_Dynamic_Human_Bodies_ICCV_2021_paper.html)]

**AD-NeRF: Audio Driven Neural Radiance Fields for Talking Head Synthesis.**<br>
*[Yudong Guo](https://yudongguo.github.io/), [Keyu Chen](http://kychern.github.io/), Sen Liang, [Yongjin Liu](https://cg.cs.tsinghua.edu.cn/people/~Yongjin/Yongjin.htm), [Hujun Bao](http://www.cad.zju.edu.cn/bao/), [Juyong Zhang](http://staff.ustc.edu.cn/~juyong/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.11078)] [[Project](https://yudongguo.github.io/ADNeRF/)] [[Video](https://www.youtube.com/watch?v=TQO2EBYXLyU)]

**In-Place Scene Labelling and Understanding With Implicit Scene Representation.**<br>
*Shuaifeng Zhi, Tristan Laidlow, Stefan Leutenegger, Andrew J. Davison.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Zhi_In-Place_Scene_Labelling_and_Understanding_With_Implicit_Scene_Representation_ICCV_2021_paper.html)]

**MINE: Towards Continuous Depth MPI with NeRF for Novel View Synthesis.**<br>
*Jiaxin Li, Zijian Feng, Qi She, Henghui Ding, Changhu Wang, Gim Hee Lee.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.14910)] [[Github](https://github.com/vincentfung13/MINE)]

**NerfingMVS: Guided Optimization of Neural Radiance Fields for Indoor Multi-view Stereo.**<br>
*Yi Wei, Shaohui Liu, Yongming Rao, Wang Zhao, Jiwen Lu, Jie Zhou.*<br>
ICCV 2021. [[PDF](https://arxiv.org/pdf/2109.01129)] [[Project](https://weiyithu.github.io/NerfingMVS/)]

**Continual Neural Mapping: Learning An Implicit Scene Representation from Sequential Observations.**<br>
*Zike Yan, Yuxin Tian, Xuesong Shi, Ping Guo, Peng Wang, Hongbin Zha.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2108.05851)]

**NeRD: Neural Reflectance Decomposition from Image Collections.**<br>
*[Mark Boss](https://markboss.me), [Raphael Braun](https://uni-tuebingen.de/en/fakultaeten/mathematisch-naturwissenschaftliche-fakultaet/fachbereiche/informatik/lehrstuehle/computergrafik/lehrstuhl/mitarbeiter/raphael-braun/), [Varun Jampani](https://varunjampani.github.io/), [Jonathan T. Barron](https://jonbarron.info/), [Ce Liu](http://people.csail.mit.edu/celiu/), [Hendrik P. A. Lensch](https://uni-tuebingen.de/en/faculties/faculty-of-science/departments/computer-science/lehrstuehle/computergrafik/computer-graphics/staff/prof-dr-ing-hendrik-lensch/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2012.03918)] [[Project](https://markboss.me/publication/2021-nerd/)] [[Github](https://github.com/cgtuebingen/NeRD-Neural-Reflectance-Decomposition)]

**Self-Calibrating Neural Radiance Fields.**<br>
*Yoonwoo Jeong, Seokjun Ahn, Christopher Choy, Animashree Anandkumar, Minsu Cho, Jaesik Park.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2108.13826)]

**BARF: Bundle-Adjusting Neural Radiance Fields.**<br>
*[Chen-Hsuan Lin](https://chenhsuanlin.bitbucket.io/), [Wei-Chiu Ma](http://people.csail.mit.edu/weichium/), Antonio Torralba, Simon Lucey.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2104.06405)] [[Github](https://github.com/chenhsuanlin/bundle-adjusting-NeRF)]

**MVSNeRF: Fast Generalizable Radiance Field Reconstruction from Multi-View Stereo.**<br>
*[Anpei Chen](https://apchenstu.github.io/), [Zexiang Xu](http://cseweb.ucsd.edu/~zex014/), Fuqiang Zhao, Xiaoshuai Zhang, [Fanbo Xiang](https://www.fbxiang.com/), [Jingyi Yu](http://vic.shanghaitech.edu.cn/vrvc/en/people/), [Hao Su](https://cseweb.ucsd.edu/~haosu/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.15595)] [[Project](https://apchenstu.github.io/mvsnerf/)] [[Github](https://github.com/apchenstu/mvsnerf)]

**GNeRF: GAN-based Neural Radiance Field without Posed Camera.**<br>
*Quan Meng, Anpei Chen, Haimin Luo, Minye Wu, Hao Su, Lan Xu, Xuming He, Jingyi Yu.*<br>
ICCV 2021 (Oral). [[PDF](https://arxiv.org/abs/2103.15606)] [[Github](https://github.com/MQ66/gnerf)]

**Semantic-NeRF: In-Place Scene Labelling and Understanding with Implicit Scene Representation.**<br>
*[Shuaifeng Zhi](http://shuaifengzhi.com/), [Tristan Laidlow](https://wp.doc.ic.ac.uk/twl15/), [Stefan Leutenegger](https://wp.doc.ic.ac.uk/sleutene/), [Andrew J. Davison](https://www.doc.ic.ac.uk/~ajd/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/pdf/2103.15875.pdf)] [[Project](https://shuaifengzhi.com/Semantic-NeRF/)]

**GRF: Learning a General Radiance Field for 3D Scene Representation and Rendering.**<br>
*[Alex Trevithick](https://alextrevithick.github.io/), [Bo Yang](https://yang7879.github.io/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2010.04595)] [[Github](https://github.com/alextrevithick/GRF)]

**Mip-NeRF: A Multiscale Representation for Anti-Aliasing Neural Radiance Fields.**<br>
*[Jonathan T. Barron](https://jonbarron.info/), [Ben Mildenhall](https://bmild.github.io/), [Matthew Tancik](https://www.matthewtancik.com/), [Peter Hedman](https://phogzone.com/cv.html), [Ricardo Martin-Brualla](http://ricardomartinbrualla.com/), [Pratul P. Srinivasan](https://pratulsrinivasan.github.io/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.13415)] [[Project](http://jonbarron.info/mipnerf)]

**PlenOctrees for Real-time Rendering of Neural Radiance Fields.**<br>
*[Alex Yu](https://alexyu.net/), [Ruilong Li](https://www.liruilong.cn/), [Matthew Tancik](https://www.matthewtancik.com/), [Hao Li](https://www.hao-li.com/), [Ren Ng](https://www2.eecs.berkeley.edu/Faculty/Homepages/yirenng.html), [Angjoo Kanazawa](https://people.eecs.berkeley.edu/~kanazawa/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.14024)] [[Project](https://alexyu.net/plenoctrees/)] [[Github](https://github.com/sxyu/plenoctree)]

**Nerfies: Deformable Neural Radiance Fields.**<br>
*[Keunhong Park](https://keunhong.com/), [Utkarsh Sinha](https://utkarshsinha.com/), [Jonathan T. Barron](https://jonbarron.info/), [Sofien Bouaziz](http://sofienbouaziz.com/), [Dan B Goldman](https://www.danbgoldman.com/), [Steven M. Seitz](https://homes.cs.washington.edu/~seitz/), [Ricardo-Martin Brualla](http://www.ricardomartinbrualla.com/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2011.12948)] [[Project](https://nerfies.github.io/)] [[Github](https://github.com/google/nerfies)]

**Unconstrained Scene Generation with Locally Conditioned Radiance Fields.**<br>
*Terrance DeVries, Miguel Angel Bautista, Nitish Srivastava, Graham W. Taylor, Joshua M. Susskind.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2104.00670)]

**Putting NeRF on a Diet: Semantically Consistent Few-Shot View Synthesis.**<br>
*[Ajay Jain](https://www.ajayj.com/), [Matthew Tancik](https://www.matthewtancik.com/), [Pieter Abbeel](https://people.eecs.berkeley.edu/~pabbeel/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2104.00677)] [[Project](https://www.ajayj.com/dietnerf)]

**KiloNeRF: Speeding up Neural Radiance Fields with Thousands of Tiny MLPs.**<br>
*Christian Reiser, Songyou Peng, Yiyi Liao, Andreas Geiger.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2011.05813)] [[Github](https://github.com/creiser/kilonerf)]

**SNARF: Differentiable Forward Skinning for Animating Non-Rigid Neural Implicit Shapes.**<br>
*Xu Chen, Yufeng Zheng, Michael J. Black, Otmar Hilliges, Andreas Geiger.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2104.03953)]

**UNISURF: Unifying Neural Implicit Surfaces and Radiance Fields for Multi-View Reconstruction.**<br>
*[Michael Oechsle](https://avg.is.tuebingen.mpg.de/person/moechsle), [Songyou Peng](https://pengsongyou.github.io/), [Andreas Geiger](http://www.cvlibs.net/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2104.10078)]

**Neural Geometric Level of Detail: Real-time Rendering with Implicit 3D Shapes.**<br>
*[Towaki Takikawa](https://tovacinni.github.io/), [Joey Litalien](https://joeylitalien.github.io/), [Kangxue Yin](https://kangxue.org/), [Karsten Kreis](https://scholar.google.de/citations?user=rFd-DiAAAAAJ), [Charles Loop](https://research.nvidia.com/person/charles-loop), [Derek Nowrouzezahrai](http://www.cim.mcgill.ca/~derek/), [Alec Jacobson](https://www.cs.toronto.edu/~jacobson/), [Morgan McGuire](https://casual-effects.com/), [Sanja Fidler](https://www.cs.toronto.edu/~fidler/).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2101.10994)] [[Project](https://nv-tlabs.github.io/nglod/)] [[Github](https://github.com/nv-tlabs/nglod)]

**Iso-Points: Optimizing Neural Implicit Surfaces with Hybrid Representations.**<br>
*[Wang Yifan](https://yifita.github.io/), [Shihao Wu](http://shihaowu.net/), [Cengiz Oztireli](https://people.inf.ethz.ch/~cengizo/), [Olga Sorkine-Hornung](https://igl.ethz.ch/people/sorkine/).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.06434)] [[Project](https://igl.ethz.ch/projects/iso-points/)] [[Github](https://github.com/yifita/iso-points)]

**STaR: Self-supervised Tracking and Reconstruction of Rigid Objects in Motion with Neural Rendering.**<br>
*[Wentao Yuan](https://wentaoyuan.github.io/), [Zhaoyang Lv](https://lvzhaoyang.github.io/), [Tanner Schmidt](https://tschmidt23.github.io/), [Steven Lovegrove](https://scholar.google.com/citations?user=JVum8voAAAAJ).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2101.01602)] [[Project](https://wentaoyuan.github.io/star/)]

**DeepSurfels: Learning Online Appearance Fusion.**<br>
*Marko Mihajlovic, Silvan Weder, Marc Pollefeys, [Martin R. Oswald](http://people.inf.ethz.ch/moswald/).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.14240)] [[Porject](https://onlinereconstruction.github.io/DeepSurfels/index.html)]

**Learning Neural Representation of Camera Pose with Matrix Representation of Pose Shift via View Synthesis.**<br>
*Yaxuan Zhu, Ruiqi Gao, Siyuan Huang, Song-Chun Zhu, Ying Nian Wu.*<br>
CVPR 2021. [[PDF](http://arxiv.org/abs/2104.01508)]

**Deformed Implicit Field: Modeling 3D Shapes with Learned Dense Correspondence.**<br>
*[Yu Deng](https://yudeng.github.io/), [Jiaolong Yang](http://jlyang.org/), [Xin Tong](https://www.microsoft.com/en-us/research/people/xtong/).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2011.13650)]

**Learned Initializations for Optimizing Coordinate-Based Neural Representations.**<br>
*[Matthew Tancik](https://www.matthewtancik.com/), [[Ben Mildenhall](https://people.eecs.berkeley.edu/~bmild/), Terrance Wang, Divi Schmidt, Pratul P. Srinivasan, [Jonathan T. Barron](https://jonbarron.info/), [Ren Ng](https://www2.eecs.berkeley.edu/Faculty/Homepages/yirenng.html).*<br>
CVPR 2021 [[PDF](https://arxiv.org/abs/2012.02189)] [[Project](https://www.matthewtancik.com/learnit)]

**Dynamic Neural Radiance Fields for Monocular 4D Facial Avatar Reconstruction.**<br>
*Guy Gafni, Justus Thies, Michael Zollhöfer, Matthias Nießner.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.03065)] [[Project](https://gafniguy.github.io/4D-Facial-Avatars/)] [[Video](https://youtu.be/m7oROLdQnjk)]

**Learned Initializations for Optimizing Coordinate-Based Neural Representations.**<br>
*[Matthew Tancik](https://www.matthewtancik.com/), [Ben Mildenhall](https://pratulsrinivasan.github.io/), [Terrance Wang](https://www.matthewtancik.com/learnit#), Divi Schmidt](https://www.matthewtancik.com/learnit#), [Pratul P. Srinivasan](https://people.eecs.berkeley.edu/~pratul/), [Jonathan T. Barron](https://jonbarron.info/), [Ren Ng](https://www2.eecs.berkeley.edu/Faculty/Homepages/yirenng.html).*<br>
CVPR 2021. [[Github](https://github.com/tancik/learnit)] [[Project](https://www.matthewtancik.com/learnit)] [[Phototourism Data](https://drive.google.com/drive/folders/1SVHKRQXiRb98q4KHVEbj8eoWxjNS2QLW?usp=sharing)]

**Neural Scene Graphs for Dynamic Scenes.**<br>
*Julian Ost, Fahim Mannan, Nils Thuerey, Julian Knodt, Felix Heide.*<br>
CVPR 2021 (Oral). [[PDF](https://arxiv.org/abs/2011.10379)] [[Project](http://light.princeton.edu/neural-scene-graphs)]

**NeRV: Neural Reflectance and Visibility Fields for Relighting and View Synthesis.**<br>
*[Pratul P. Srinivasan](https://pratulsrinivasan.github.io/), [Boyang Deng](https://boyangdeng.com/), [Xiuming Zhang](https://people.csail.mit.edu/xiuming/), Matthew Tancik, Ben Mildenhall, Jonathan T. Barron.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.03927)] [[Project](https://people.eecs.berkeley.edu/~pratul/nerv)]

**pixelNeRF: Neural Radiance Fields from One or Few Images.**<br>
*[Alex Yu](https://alexyu.net/), Vickie Ye, Matthew Tancik, Angjoo Kanazawa.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.02190)] [[Project](https://alexyu.net/pixelnerf)]

**AutoInt: Automatic Integration for Fast Neural Volume Rendering.**<br>
*David B. Lindell, Julien N. P. Martel, Gordon Wetzstein.*<br>
CVPR 2021 (oral). [[PDF](https://arxiv.org/abs/2012.01714)] [[Project](http://www.computationalimaging.org/publications/automatic-integration/)]

**DeRF: Decomposed Radiance Fields.**<br>
*Daniel Rebain, Wei Jiang, Soroosh Yazdani, Ke Li, Kwang Moo Yi, Andrea Tagliasacchi.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2011.12490)] [[Project](https://ubc-vision.github.io/derf/)]

**D-NeRF: Neural Radiance Fields for Dynamic Scenes.**<br>
*[Albert Pumarola](https://www.albertpumarola.com/), [Enric Corona](https://www.iri.upc.edu/people/ecorona/), [Gerard Pons-Moll](http://virtualhumans.mpi-inf.mpg.de/), [Francesc Moreno-Noguer](http://www.iri.upc.edu/people/fmoreno/).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2011.13961)] [[Project](https://www.albertpumarola.com/research/D-NeRF/index.html)] [[Github](https://github.com/albertpumarola/D-NeRF)] [[Data](https://www.dropbox.com/s/0bf6fl0ye2vz3vr/data.zip?dl=0)]

**Space-time Neural Irradiance Fields for Free-Viewpoint Video.**<br>
*[Wenqi Xian](https://www.cs.cornell.edu/~wenqixian/), [Jia-Bin Huang](https://filebox.ece.vt.edu/~jbhuang/), [Johannes Kopf](https://johanneskopf.de/), [Changil Kim](https://changilkim.com/).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2011.12950)] [[Project](https://video-nerf.github.io/)]

**GIRAFFE: Representing Scenes as Compositional Generative Neural Feature Fields.**<br>
*Michael Niemeyer, Andreas Geiger.*<br>
CVPR 2021 (Best Paper). [[PDF](https://arxiv.org/abs/2011.12100)] [[Project](https://m-niemeyer.github.io/project-pages/giraffe/index.html)] [[Github](https://github.com/autonomousvision/giraffe)]

**DONeRF: Towards Real-Time Rendering of Neural Radiance Fields using Depth Oracle Networks.**<br>
*Thomas Neff, Pascal Stadlbauer, Mathias Parger, Andreas Kurz, Chakravarty R. Alla Chaitanya, Anton Kaplanyan, Markus Steinberger.*<br>
Computer Graphics Forum (EGSR) 2021. [[PDF](https://arxiv.org/abs/2103.03231)] [[Project](https://depthoraclenerf.github.io/)]

**iNeRF: Inverting Neural Radiance Fields for Pose Estimation.**<br>
*[Lin Yen-Chen](http://yenchenlin.me/), Pete Florence, Jonathan T. Barron, Alberto Rodriguez, Phillip Isola, Tsung-Yi Lin.*<br>
IROS 2021. [[PDF](https://arxiv.org/abs/2012.05877)] [[Project](http://yenchenlin.me/inerf/)]

**JIIF: Joint Implicit Image Function for Guided Depth Super-Resolution.**<br>
*Jiaxiang Tang, Xiaokang Chen, Gang Zeng.*<br>
ACM MM 2021. [[PDF](https://arxiv.org/abs/2107.08717)] [[Github](https://github.com/ashawkey/jiif)]

**Spline Positional Encoding for Learning 3D Implicit Signed Distance Fields.**<br>
*Peng-Shuai Wang, Yang Liu, Yu-Qi Yang, and Xin Tong.*<br>
IJCAI 2021. [[PDF](https://arxiv.org/abs/2106.01553)]

**Convolutional Neural Opacity Radiance Fields.**<br>
*Haimin Luo, Anpei Chen, Qixuan Zhang, Bai Pang, Minye Wu, Lan Xu, Jingyi Yu.*<br>
ICCP 2021. [[PDF](https://arxiv.org/abs/2104.01772)]

**O-CNN: Unsupervised 3D Learning for Shape Analysis via Multiresolution Instance Discrimination.**<br>
*[Peng-Shuai Wang](https://wang-ps.github.io/), Yu-Qi Yang, Qian-Fang Zou, Zhirong Wu, Yang Liu, Xin Tong.*<br>
AAAI 2021. [[PDF](https://arxiv.org/abs/2008.01068)] [[Github](https://github.com/microsoft/O-CNN)]

**ShaRf: Shape-conditioned Radiance Fields from a Single View.**<br> 
*[Konstantinos Rematas](http://www.krematas.com/), [Ricardo Martin-Brualla](http://ricardomartinbrualla.com/), [Vittorio Ferrari](https://sites.google.com/view/vittoferrari).*<br>
ICML 2021. [[PDF](https://arxiv.org/abs/2102.08860)] [[Project](http://www.krematas.com/sharf/)]

**PolyGen: An Autoregressive Generative Model of 3D Meshes.**<br>
*Charlie Nash, Yaroslav Ganin, S. M. Ali Eslami, Peter W. Battaglia.*<br>
ICML 2020. [[PDF](https://arxiv.org/abs/2002.10880)] [[Github](https://github.com/deepmind/deepmind-research/tree/master/polygen)]

**Learning Implicit Surface Light Fields.**<br>
*Michael Oechsle, Michael Niemeyer, Lars Mescheder, Thilo Strauss, Andreas Geiger.*<br>
3DV 2020. [[PDF](https://arxiv.org/abs/2003.12406)] [[Github](https://github.com/autonomousvision/cslf)]

**NSVF: Neural Sparse Voxel Fields.**<br>
*[Lingjie Liu](https://lingjie0206.github.io/), [Jiatao Gu](http://jiataogu.me/), Kyaw Zaw Lin, [Tat-Seng Chua](https://www.chuatatseng.com/), [Christian Theobalt](http://people.mpi-inf.mpg.de/~theobalt/).*<br>
NeurIPS 2020. [[PDF](https://arxiv.org/abs/2007.11571)] [[Project](https://lingjie0206.github.io/papers/NSVF/)] [[Github](https://github.com/facebookresearch/NSVF)]

**BlockGAN: Learning 3D Object-Aware Scene Representations from Unlabelled Images.**<br>
*[Thu Nguyen-Phuoc](https://monkeyoverflow.com/about/), [Christian Richardt](https://richardt.name/), [Long Mai](https://mai-t-long.com/), [Yong-Liang Yang](http://yongliangyang.net/), [Niloy Mitra](http://www0.cs.ucl.ac.uk/staff/n.mitra/index.html).*<br>
NeurIPS 2020. [[PDF](https://arxiv.org/abs/2002.08988)] [[Project](https://www.monkeyoverflow.com/#/blockgan/)] [[Github](https://github.com/thunguyenphuoc/BlockGAN)]

**Neural Unsigned Distance Fields for Implicit Function Learning.**<br>
*Julian Chibane, Aymen Mir, Gerard Pons-Moll.*<br>
NeurIPS 2020. [[PDF](https://arxiv.org/abs/2010.13938)] [[Github](https://virtualhumans.mpi-inf.mpg.de/ndf/)]

**SIREN: Implicit Neural Representations with Periodic Activation Functions.**<br>
*[Vincent Sitzmann](https://vsitzmann.github.io/), [Julien N. P. Martel](http://www.jmartel.net/), [Alexander W. Bergman](http://alexanderbergman7.github.io/), [David B. Lindell](http://www.davidlindell.com/), [Gordon Wetzstein](https://stanford.edu/~gordonwz/).*<br>
NeurIPS 2020 (Oral). [[PDF](https://arxiv.org/abs/2006.09661)] [[Project](https://vsitzmann.github.io/siren)] [[Github](https://github.com/vsitzmann/siren)] [[Data](https://drive.google.com/drive/folders/1_iq__37-hw7FJOEUK1tX7mdp8SKB368K?usp=sharing)]

**GRAF: Generative Radiance Fields for 3D-Aware Image Synthesis.**<br>
*Katja Schwarz, Yiyi Liao, Michael Niemeyer, Andreas Geiger.*<br>
NeurIPS 2020. [[PDF](https://arxiv.org/abs/2007.02442)] [[Project](https://avg.is.tuebingen.mpg.de/publications/schwarz2020neurips)] [[Github](https://github.com/autonomousvision/graf)]

**Learning 3D Part Assembly from a Single Image.**<br>
*[Yichen Li](http://cs.stanford.edu/~liyichen/), [Kaichun Mo](http://cs.stanford.edu/~kaichun/), [Lin Shao](https://linsats.github.io/), [Minhyuk Sung](https://mhsung.github.io/), [Leonidas Guibas](https://geometry.stanford.edu/member/guibas/).*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2003.09754)] [[Github](https://github.com/AntheaLi/3DPartAssembly)]

**CoReNet: Coherent 3D Scene Reconstruction From a Single RGB Image.**<br>
*Stefan Popov, Pablo Bauszat, Vittorio Ferrari.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2004.12989)] [[Github](https://github.com/google-research/corenet)]

**Geometric Correspondence Fields: Learned Differentiable Rendering for 3D Pose Refinement in the Wild.**<br>
*Alexander Grabner, Yaming Wang, Peizhao Zhang, Peihong Guo, Tong Xiao, Peter Vajda, Peter M. Roth, Vincent Lepetit.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2007.08939)]

**Curriculum DeepSDF.**<br>
*Yueqi Duan, Haidong Zhu, He Wang, Li Yi, Ram Nevatia, Leonidas J. Guibas.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2003.08593)] [[Github](https://github.com/haidongz-usc/Curriculum-DeepSDF)]

**PatchNets: Patch-Based Generalizable Deep Implicit 3D Shape Representations.**<br>
*Edgar Tretschk, Ayush Tewari, Vladislav Golyanik, Michael Zollhöfer, Carsten Stoll, Christian Theobalt.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2008.01639)] [[Github](https://github.com/edgar-tr/patchnets)] [[Project](http://gvv.mpi-inf.mpg.de/projects/PatchNets/)]

**LIMP: Learning Latent Shape Representations with Metric Preservation Priors.**<br>
*Luca Cosmo, Antonio Norelli, Oshri Halimi, Ron Kimmel, Emanuele Rodolà.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2003.12283)]

**Convolutional Occupancy Networks.**<br>
*[Songyou Peng](https://pengsongyou.github.io/), [Michael Niemeyer](https://m-niemeyer.github.io/), [Lars Mescheder](https://is.tuebingen.mpg.de/person/lmescheder), [Marc Pollefeys](https://people.inf.ethz.ch/pomarc/), [Andreas Geiger](http://www.cvlibs.net/).*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2003.04618)] [[Project](https://pengsongyou.github.io/conv_onet)] [[Github](https://github.com/autonomousvision/convolutional_occupancy_networks)]

**Equivariant Neural Rendering.**<br>
*[Emilien Dupont](https://emiliendupont.github.io/), Miguel Angel Bautista, [Alex Colburn](https://www.colburn.org/), Aditya Sankar, [Carlos Guestrin](https://homes.cs.washington.edu/~guestrin/), Josh Susskind, [Qi Shan](http://shanqi.github.io/).*<br>
ICML 2020. [[PDF](https://arxiv.org/abs/2006.07630)] [[Github](https://github.com/apple/ml-equivariant-neural-rendering)]

**Pix2Shape: Towards Unsupervised Learning of 3D Scenes from Images using a View-based Representation.**<br>
*Sai Rajeswar, Fahim Mannan, Florian Golemo, Jérôme Parent-Lévesque, David Vazquez, Derek Nowrouzezahrai, Aaron Courville.*<br>
IJCV 2020. [[PDF](https://arxiv.org/abs/2003.14166)]

**Local Deep Implicit Functions for 3D Shape.**<br>
*Kyle Genova, Forrester Cole, Avneesh Sud, Aaron Sarna, Thomas Funkhouser.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/1912.06126)]

**Differentiable Volumetric Rendering (DVR): Learning Implicit 3D Representations without 3D Supervision.**<br>
*Michael Niemeyer, Lars Mescheder, Michael Oechsle, Andreas Geiger.*<br>
CVPR 2020. [[PDF](http://www.cvlibs.net/publications/Niemeyer2020CVPR.pdf)] [[Github](https://github.com/autonomousvision/differentiable_volumetric_rendering)]

**Single-View View Synthesis with Multiplane Images.**<br>
*Richard Tucker and Noah Snavely.*<br>
CVPR 2020. [[PDF](https://single-view-mpi.github.io/single_view_mpi.pdf)] [[Project](https://single-view-mpi.github.io/)]

**PIFuHD: Multi-Level Pixel-Aligned Implicit Function for High-Resolution 3D Human Digitization.**<br>
*Shunsuke Saito, Tomas Simon, Jason Saragih, Hanbyul Joo.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2004.00452)] [[Project](https://shunsukesaito.github.io/PIFuHD)] [[Github](https://github.com/facebookresearch/pifuhd)]

**DualSDF: Semantic Shape Manipulation using a Two-Level Representation.**<br>
*Zekun Hao, Hadar Averbuch-Elor, Noah Snavely, Serge Belongie.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2004.02869)]

**Learning a Neural 3D Texture Space from 2D Exemplars.**<br>
*Philipp Henzler, Niloy J. Mitra, Tobias Ritschel.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/1912.04158)] [[Project](https://geometry.cs.ucl.ac.uk/projects/2020/neuraltexture/)]

**Neural Contours: Learning to Draw Lines from 3D Shapes.**<br>
*[Difan Liu](https://people.cs.umass.edu/~dliu/), Mohamed Nabail, [Aaron Hertzmann](https://www.dgp.toronto.edu/~hertzman/), [Evangelos Kalogerakis](https://people.cs.umass.edu/~kalo/).*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2003.10333)] [[Github](https://github.com/DifanLiu/NeuralContours)]

**Learning View Priors for Single-view 3D Reconstruction.**<br>
*Hiroharu Kato, Tatsuya Harada.*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1811.10719)] [[Project](http://hiroharu-kato.com/projects_en/view_prior_learning.html)] [[Github](https://github.com/hiroharu-kato/view_prior_learning)]

**IM-Net: Learning Implicit Fields for Generative Shape Modeling.**<br>
*Zhiqin Chen, Hao Zhang.*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1812.02822)] [[Project](https://www.sfu.ca/~zhiqinc/imgan/Readme.html)] [[Github](https://github.com/czq142857/implicit-decoder)]

**C3DPO: Canonical 3D Pose Networks for Non-Rigid Structure From Motion.**<br>
*David Novotny, Nikhila Ravi, Benjamin Graham, Natalia Neverova, Andrea Vedaldi.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1909.02533)] [[Github](https://github.com/facebookresearch/c3dpo_nrsfm)] [[Project](https://research.fb.com/publications/c3dpo-canonical-3d-pose-networks-for-non-rigid-structure-from-motion/)]

**CSM: Canonical Surface Mapping via Geometric Cycle Consistency.**<br>
*Nilesh Kulkarni, Abhinav Gupta, Shubham Tulsiani.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1907.10043)] [[Github](https://nileshkulkarni.github.io/csm/)] [[Project](https://nileshkulkarni.github.io/csm/)]

**NASA: Neural Articulated Shape Approximation.**<br>
*[Boyang Deng](https://research.google/people/BoyangDeng/), JP Lewis, Timothy Jeruzalski, Gerard Pons-Moll, Geoffrey Hinton, Mohammad Norouzi, Andrea Tagliasacchi.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/1912.03207)] [[Project](https://virtualhumans.mpi-inf.mpg.de/nasa/)] [[Github](https://github.com/tensorflow/graphics/tree/master/tensorflow_graphics/projects/nasa)]
 
**NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis.**<br>
*[Ben Mildenhall](http://people.eecs.berkeley.edu/~bmild/), [Pratul P. Srinivasan](https://people.eecs.berkeley.edu/~pratul/), [Matthew Tancik](http://www.matthewtancik.com/), [Jonathan T. Barron](https://jonbarron.info/), [Ravi Ramamoorthi](http://cseweb.ucsd.edu/~ravir/), [Ren Ng](https://www2.eecs.berkeley.edu/Faculty/Homepages/yirenng.html).*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2003.08934)] [[Project](http://tancik.com/nerf)] [[Gtihub-Tensorflow](https://github.com/bmild/nerf)] [[krrish94-PyTorch](https://github.com/krrish94/nerf-pytorch)] [[yenchenlin-PyTorch](https://github.com/yenchenlin/nerf-pytorch)]

**VCN: Volumetric Correspondence Networks for Optical Flow.**<br>
*Gengshan Yang, Deva Ramanan.*<br>
NeurIPS 2019. [[PDF](http://www.contrib.andrew.cmu.edu/~gengshay/wordpress/wp-content/uploads/2019/11/vcn.pdf)] [[GitHub](https://github.com/gengshan-y/VCN)] [[Project](http://www.contrib.andrew.cmu.edu/~gengshay/neurips19flow)]

**Scene Representation Networks: Continuous 3D-Structure-Aware Neural Scene Representations.**<br>
*[Vincent Sitzmann](https://vsitzmann.github.io/), Michael Zollhöfer, Gordon Wetzstein.*<br>
NeurIPS 2019 (Oral, Honorable Mention "Outstanding New Directions").
[[PDF](http://arxiv.org/abs/1906.01618)] [[Project](https://github.com/vsitzmann/scene-representation-networks)] [[Github](https://github.com/vsitzmann/scene-representation-networks)] [[Dataset](https://drive.google.com/drive/folders/1OkYgeRcIcLOFu1ft5mRODWNQaPJ0ps90?usp=sharing)]

**Transformable Bottleneck Networks.**<br>
*Kyle Olszewski, Sergey Tulyakov, Oliver Woodford, Hao Li, Linjie Luo.*<br>
ICCV 2019. [[PDF](http://openaccess.thecvf.com/content_ICCV_2019/papers/Olszewski_Transformable_Bottleneck_Networks_ICCV_2019_paper.pdf)]

**Equivariant Multi-View Networks.**<br>
*Carlos Esteves, Yinshuang Xu, Christine Allen-Blanchette, Kostas Daniilidis.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1904.00993)]

**PIFu: Pixel-Aligned Implicit Function for High-Resolution Clothed Human Digitization.**<br>
*Shunsuke Saito, Zeng Huang, Ryota Natsume, Shigeo Morishima, Angjoo Kanazawa, Hao Li.*<br>
ICCV 2019. [[PDF](https://arxiv.org/pdf/1905.05172.pdf)] [[Project](shunsukesaito.github.io/PIFu)] [[Github](https://github.com/shunsukesaito/PIFu)]

**Occupancy Flow: 4D Reconstruction by Learning Particle Dynamics.**<br>
*Michael Niemeyer, Lars Mescheder, Michael Oechsle, Andreas Geiger.*<br>
ICCV 2019. [[PDF](http://www.cvlibs.net/publications/Niemeyer2019ICCV.pdf)] [[Project](https://avg.is.tuebingen.mpg.de/publications/niemeyer2019iccv)] [[Github](https://github.com/autonomousvision/occupancy_flow)]

**DeepSDF: Learning Continuous Signed Distance Functions for Shape Representation.**<br>
*eong Joon Park, Peter Florence, Julian Straub, Richard Newcombe, Steven Lovegrove.*<br>
CVPR 2019. [[PDF](http://openaccess.thecvf.com/content_CVPR_2019/html/Park_DeepSDF_Learning_Continuous_Signed_Distance_Functions_for_Shape_Representation_CVPR_2019_paper.html)] [[Github](https://github.com/facebookresearch/DeepSDF)] 

**DeepVoxels: Learning Persistent 3D Feature Embeddings.**<br>
*Vincent Sitzmann, Justus Thies, Felix Heide, Matthias Nießner, Gordon Wetzstein, Michael Zollhöfer.*<br>
CVPR 2019 (Oral). [[Project](http://vsitzmann.github.io/deepvoxels/)] [[PDF](https://arxiv.org/abs/1812.01024)] [[Code](https://github.com/vsitzmann/deepvoxels)]

**Occupancy Networks: Learning 3D Reconstruction in Function Space.**<br>
*Lars Mescheder, Michael Oechsle, Michael Niemeyer, Sebastian Nowozin, Andreas Geiger.*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1812.03828)] [[Github](http://avg.is.tuebingen.mpg.de/publications/occupancy-networks)]

**LLFF: Local Light Field Fusion: Practical View Synthesis with Prescriptive Sampling Guidelines.**<br>
*[Ben Mildenhall](http://people.eecs.berkeley.edu/~bmild/), Pratul Srinivasan, Rodrigo Ortiz-Cayon, Nima Khademi Kalantari, Ravi Ramamoorthi, Ren Ng, Abhishek Kar.*<br>
TOG 2019. [[PDF](https://arxiv.org/abs/1905.00889)] [[Project](https://people.eecs.berkeley.edu/~bmild/llff/)] [[Github](https://github.com/Fyusion/LLFF)]

**Neural Volumes: Learning Dynamic Renderable Volumes from Images.**<br>
*Stephen Lombardi, Tomas Simon, Jason Saragih, Gabriel Schwartz, Andreas Lehrmann, Yaser Sheikh.*<br>
TOG 2019. [[PDF](https://arxiv.org/abs/1906.07751)] [[Github](https://github.com/facebookresearch/neuralvolumes)]

## Novel-View Synthesis for Objects and Scenes

[Novel-View Synthesis](https://paperswithcode.com/task/novel-view-synthesis/codeless)

### By Implicit Neural Representations

**PVSeRF: Joint Pixel-, Voxel- and Surface-Aligned Radiance Field for Single-Image Novel View Synthesis.**<br>
*Xianggang Yu, Jiapeng Tang, Yipeng Qin, Chenghong Li, Linchao Bao, Xiaoguang Han, Shuguang Cui.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.04879)]

**3D-Aware Semantic-Guided Generative Model for Human Synthesis.**<br>
*Jichao Zhang, Enver Sangineto, Hao Tang, Aliaksandr Siarohin, Zhun Zhong, Nicu Sebe, Wei Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.01422)]

**Neural Rays for Occlusion-aware Image-based Rendering.**<br>
*Yuan Liu, Sida Peng, Lingjie Liu, Qianqian Wang, Peng Wang, Christian Theobalt, Xiaowei Zhou, Wenping Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2107.13421)]

**LiveView: Dynamic Target-Centered MPI for View Synthesis.**<br>
*Sushobhan Ghosh, Zhaoyang Lv, Nathan Matsuda, Lei Xiao, Andrew Berkovich, Oliver Cossairt.*<br>
arxiv 2021. [[PDF](https://arxiv.org/pdf/2107.05113.pdf)]

**NeLF: Practical Novel View Synthesis with Neural Light Field.**<br>
*Celong Liu, Zhong Li, Junsong Yuan, Yi Xu.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2105.07112)]

**NeMI: Unifying Neural Radiance Fields with Multiplane Images for Novel View Synthesis.**<br>
*Jiaxin Li, Zijian Feng, Qi She, Henghui Ding, Changhu Wang, Gim Hee Lee.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2103.14910)] [[Project](https://vincentfung13.github.io/projects/nemi/)]

**Novel-View Synthesis of Human Tourist Photos.**<br>
*Jonathan Freer, Kwang Moo Yi, Wei Jiang, Jongwon Choi, Hyung Jin Chang.*<br>
WACV 2022. [[PDF](https://openaccess.thecvf.com/content/WACV2022/papers/Freer_Novel-View_Synthesis_of_Human_Tourist_Photos_WACV_2022_paper.pdf)]

**Fast and Explicit Neural View Synthesis.**<br>
*Pengsheng Guo, Miguel Angel Bautista, Alex Colburn, Liang Yang, Daniel Ulbricht, Joshua M. Susskind, Qi Shan.*<br>
WACV 2022. [[PDF](https://arxiv.org/abs/2107.05775)]

**LENS: Localization enhanced by NeRF synthesis.**<br>
*Arthur Moreau, Nathan Piasco, Dzmitry Tsishkou, Bogdan Stanciulescu, Arnaud de La Fortelle.*<br>
CoRL 2021. [[PDF](https://arxiv.org/abs/2110.06558)]

**Dynamic View Synthesis from Dynamic Monocular Video.**<br>
*[Chen Gao](http://chengao.vision/), [Ayush Saraf](https://www.linkedin.com/in/ayush29feb/), [Johannes Kopf](http://johanneskopf.de/), [Jia-Bin Huang](https://filebox.ece.vt.edu/~jbhuang/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2105.06468)] [[Project](https://free-view-video.github.io/)]

**MINE: Towards Continuous Depth MPI with NeRF for Novel View Synthesis.**<br>
*Jiaxin Li, Zijian Feng, Qi She, Henghui Ding, Changhu Wang, Gim Hee Lee.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.14910)] [[Github](https://github.com/vincentfung13/MINE)]

**NeRFlow: Neural Radiance Flow for 4D View Synthesis and Video Processing.**<br>
*Yilun Du, Yinan Zhang, Hong-Xing Yu, Joshua B. Tenenbaum, Jiajun Wu.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2012.09790)] [[Project](https://yilundu.github.io/nerflow/)]

**Non-Rigid Neural Radiance Fields: Reconstruction and Novel View Synthesis of a Dynamic Scene From Monocular Video.**<br>
*Edgar Tretschk, Ayush Tewari, Vladislav Golyanik, Michael Zollhofer, Christoph Lassner, Christian Theobalt.*<br>
ICCV 2021 (oral). [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Tretschk_Non-Rigid_Neural_Radiance_Fields_Reconstruction_and_Novel_View_Synthesis_of_ICCV_2021_paper.html)]


**Baking Neural Radiance Fields for Real-Time View Synthesis.**<br>
*[Peter Hedman](https://phogzone.com/), [Pratul P. Srinivasan](https://pratulsrinivasan.github.io/), [Ben Mildenhall](https://bmild.github.io/), [Jonathan T. Barron](https://jonbarron.info/), [Paul Debevec](https://www.pauldebevec.com/).*<br>
ICCV 2021 (oral). [[PDF](https://arxiv.org/abs/2103.14645)] [[Project](https://nerf.live/)]

**Animatable Neural Radiance Fields for Human Body Modeling.**<br>
*[Sida Peng](https://pengsida.net/), Junting Dong, Qianqian Wang, Shangzhan Zhang, Qing Shuai, Hujun Bao, Xiaowei Zhou.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2105.02872)] [[Project](https://zju3dv.github.io/animatable_nerf/)] [[Github](https://github.com/zju3dv/animatable_nerf)]

**3D Shape Generation with Grid-based Implicit Functions.**<br>
*Moritz Ibing, Isaak Lim, Leif Kobbelt.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2107.10607)]

**Stereo Radiance Fields (SRF): Learning View Synthesis for Sparse Views of Novel Scenes.**<br>
*Julian Chibane, Aayush Bansal, Verica Lazova, Gerard Pons-Moll.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2104.06935)]

**ID-Unet: Iterative Soft and Hard Deformation for View Synthesis.**<br>
*Mingyu Yin, Li Sun, Qingli Li.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.02264)]

**NSFF: Neural Scene Flow Fields for Space-Time View Synthesis of Dynamic Scenes.**<br>
*[Zhengqi Li](https://www.cs.cornell.edu/~zl548/), [Simon Niklaus](https://sniklaus.com/welcome), [Noah Snavely](https://www.cs.cornell.edu/~snavely/), [Oliver Wang](https://research.adobe.com/person/oliver-wang/).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2011.13084)] [[Project](http://www.cs.cornell.edu/~zl548/NSFF)] [[Github](https://github.com/zhengqili/Neural-Scene-Flow-Fields)]

**Neural Body: Implicit Neural Representations with Structured Latent Codes for Novel View Synthesis of Dynamic Humans.**<br>
*[Sida Peng](https://pengsida.net/), Yuanqing Zhang, Yinghao Xu, Qianqian Wang, Qing Shuai, Hujun Bao, Xiaowei Zhou.*<br>
CVPR 2021 (Best paper candidate). [[PDF](https://arxiv.org/abs/2012.15838)] [[Project](https://zju3dv.github.io/neuralbody/)] [[Github](https://github.com/zju3dv/neuralbody)]

**NeRF in the Wild: Neural Radiance Fields for Unconstrained Photo Collections.**<br>
*[Ricardo Martin-Brualla](http://www.ricardomartinbrualla.com/), [Noha Radwan](https://scholar.google.com/citations?user=g98QcZUAAAAJ&hl=en), [Mehdi S. M. Sajjadi](https://research.google/people/105804/), [Jonathan T. Barron](https://jonbarron.info/), [Alexey Dosovitskiy](https://scholar.google.com/citations?user=FXNJRDoAAAAJ&hl=en), [Daniel Duckworth](http://www.stronglyconvex.com/about.html).*<br>
CVPR 2021 (oral). [[PDF](https://arxiv.org/abs/2008.02268)] [[Github](https://nerf-w.github.io/)]

**pixelNeRF: Neural Radiance Fields from One or Few Images.**<br>
*Alex Yu, Vickie Ye, Matthew Tancik, Angjoo Kanazawa.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.02190)] [[Project](https://alexyu.net/pixelnerf/)] [[Github](https://github.com/sxyu/pixel-nerf)]

**DyNeRF: Neural 3D Video Synthesis.**<br>
*[Tianye Li](https://tianyeli.github.io/), [Mira Slavcheva](https://scholar.google.de/citations?user=cJKcPcIAAAAJ&hl=en), [Michael Zollhoefer](https://zollhoefer.com/), [Simon Green](https://scholar.google.com/citations?user=VmHZtsEAAAAJ&hl=en), [Christoph Lassner](https://christophlassner.de/), [Changil Kim](https://changilkim.com/), [Tanner Schmidt](https://tschmidt23.github.io/), [Steven Lovegrove](https://scholar.google.com/citations?hl=en&user=JVum8voAAAAJ), [Michael Goesele](https://scholar.google.com/citations?user=56UhAooAAAAJ&hl=en), [Zhaoyang Lv](https://lvzhaoyang.github.io/).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2103.02597)] [[Project](https://neural-3d-video.github.io/)]

**NeRF++: Analyzing and Improving Neural Radiance Fields.**<br>
*Kai Zhang, Gernot Riegler, Noah Snavely, Vladlen Koltun.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2010.07492)] [[Github](https://github.com/Kai-46/nerfplusplus)]

**X-Fields: Implicit Neural View-, Light- and Time-Image Interpolation.**<br>
*MOJTABA BEMANA, KAROL MYSZKOWSKI, HANS-PETER SEIDEL, TOBIAS RITSCHEL.*<br>
TOG 2020. [[PDF](http://xfields.mpi-inf.mpg.de/paper/X_Fields__siggasia_2020.pdf)]

**GRAF: Generative Radiance Fields for 3D-Aware Image Synthesis.**<br>
*Katja Schwarz, Yiyi Liao, Michael Niemeyer, Andreas Geiger.*<br>
NeurIPS 2020. [[PDF](https://arxiv.org/abs/2007.02442)] [[Project](https://avg.is.tuebingen.mpg.de/publications/schwarz2020neurips)] [[Github](https://github.com/autonomousvision/graf)]

**NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis.**<br>
*[Ben Mildenhall](http://people.eecs.berkeley.edu/~bmild/), [Pratul P. Srinivasan](https://people.eecs.berkeley.edu/~pratul/), [Matthew Tancik](http://www.matthewtancik.com/), [Jonathan T. Barron](https://jonbarron.info/), [Ravi Ramamoorthi](http://cseweb.ucsd.edu/~ravir/), [Ren Ng](https://www2.eecs.berkeley.edu/Faculty/Homepages/yirenng.html).*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2003.08934)] [[Project](http://tancik.com/nerf)] [[Gtihub-Tensorflow](https://github.com/bmild/nerf)] [[krrish94-PyTorch](https://github.com/krrish94/nerf-pytorch)] [[yenchenlin-PyTorch](https://github.com/yenchenlin/nerf-pytorch)]

### From Single Image

**Unsupervised Novel View Synthesis from a Single Image.**<br>
*Pierluigi Zama Ramirez, Alessio Tonioni, Federico Tombari.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2102.03285)]

**Infinite Nature: Perpetual View Generation of Natural Scenes from a Single Image.**<br>
*[Andrew Liu](https://andrewhliu.github.io/), Richard Tucker, Varun Jampani, Ameesh Makadia, Noah Snavely, Angjoo Kanazawa.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2012.09855)] [[Project](https://infinite-nature.github.io/)] [[Gtihub](https://github.com/google-research/google-research/blob/master/infinite_nature)]

**Worldsheet: Wrapping the World in a 3D Sheet for View Synthesis from a Single Image.**<br>
*[Ronghang Hu](https://ronghanghu.com/), [Deepak Pathak](https://www.cs.cmu.edu/~dpathak/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2012.09854)] [[Project](https://worldsheet.github.io/)]

**Layout-Guided Novel View Synthesis from a Single Indoor Panorama.**<br>
*Jiale Xu, Jia Zheng, Yanyu Xu, Rui Tang, Shenghua Gao.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.17022)]

**pixelNeRF: Neural Radiance Fields from One or Few Images.**<br>
*Alex Yu, Vickie Ye, Matthew Tancik, Angjoo Kanazawa.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.02190)] [[Project](https://alexyu.net/pixelnerf)]

**ShaRF: Shape-conditioned Radiance Fields from a Single View.**<br>
*Konstantinos Rematas, Ricardo Martin-Brualla, Vittorio Ferrari.*<br>
ICML 2021. [[PDF](https://arxiv.org/abs/2102.08860)] [[Project](http://www.krematas.com/sharf/index.html)]

**Generative View Synthesis: From Single-view Semantics to Novel-view Images.**<br>
*Tewodros Habtegebrial, Varun Jampani, Orazio Gallo, Didier Stricker.*<br>
NeurIPS 2020. [[PDF](https://arxiv.org/abs/2008.09106)] [[Project](https://gvsnet.github.io/)]

### Others

**Geometry-Free View Synthesis: Transformers and no 3D Priors.**<br>
*[Robin Rombach](https://github.com/rromb), [Patrick Esser](https://github.com/pesser), [Björn Ommer](https://hci.iwr.uni-heidelberg.de/Staff/bommer).*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2104.07652)] [[Github](https://github.com/CompVis/geometry-free-view-synthesis)]

**Deep View Synthesis via Self-Consistent Generative Network.**<br>
*Zhuoman Liu, Wei Jia, Ming Yang, Peiyao Luo, Yong Guo, Mingkui Tan.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2101.10844)]

**Vid2Actor: Free-viewpoint Animatable Person Synthesis from Video in the Wild.**<br>
*Chung-Yi Weng, Brian Curless, Ira Kemelmacher-Shlizerman.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.12884)] [[Project](https://grail.cs.washington.edu/projects/vid2actor/)] [[Video](https://youtu.be/Zec8Us0v23o)]

**Object-Centric Neural Scene Rendering.**<br>
*Michelle Guo, Alireza Fathi, Jiajun Wu, Thomas Funkhouser.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.08503)] [[Project](https://shellguo.com/osf)]

**Neural Point-Based Graphics.**<br>
*Kara-Ali Aliev, Artem Sevastopolsky, Maria Kolos, Dmitry Ulyanov, Victor Lempitsky.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/1906.08240)] [[Project](https://saic-violet.github.io/npbg/)] [[Github](https://github.com/alievk/npbg)]

**RGBD-Net: Predicting Color and Depth Images for Novel Views Synthesis.**<br>
*Phong Nguyen, Animesh Karnewar, Lam Huynh, Esa Rahtu, Jiri Matas, Janne Heikkila.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2011.14398)] [[GIthub](https://github.com/phongnhhn92/RGBDNet)]

**SofGAN: A Portrait Image Generator with Dynamic Styling.**<br>
*Anpei Chen, Ruiyang Liu, Ling Xie, Jingyi Yu.*<br>
TOG 2021. [[PDF](https://arxiv.org/abs/2007.03780)] [[Github](https://github.com/apchenstu/sofgan)]

**Dynamic View Synthesis From Dynamic Monocular Video.**<br>
*Chen Gao, Ayush Saraf, Johannes Kopf, Jia-Bin Huang.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Gao_Dynamic_View_Synthesis_From_Dynamic_Monocular_Video_ICCV_2021_paper.html)]

**Embedding Novel Views in a Single JPEG Image.**<br>
*Yue Wu, Guotao Meng, Qifeng Chen.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Wu_Embedding_Novel_Views_in_a_Single_JPEG_Image_ICCV_2021_paper.html)]

**Learning To Stylize Novel Views.**<br>
*Hsin-Ping Huang, Hung-Yu Tseng, Saurabh Saini, Maneesh Singh, Ming-Hsuan Yang.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Huang_Learning_To_Stylize_Novel_Views_ICCV_2021_paper.html)]

**Deep 3D Mask Volume for View Synthesis of Dynamic Scenes.**<br>
*Kai-En Lin, Lei Xiao, Feng Liu, Guowei Yang, Ravi Ramamoorthi.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2108.13408)] [[Project](https://cseweb.ucsd.edu//~viscomp/projects/ICCV21Deep/)]

**PixelSynth: Generating a 3D-Consistent Experience from a Single Image.**<br>
*[Chris Rockwell](https://crockwell.github.io/), [David F. Fouhey](https://web.eecs.umich.edu/~fouhey/), [Justin Johnson](https://web.eecs.umich.edu/~justincj/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2108.05892)] [[Project](https://crockwell.github.io/pixelsynth/)]

**Self-Supervised Visibility Learning for Novel View Synthesis.**<br>
*Yujiao Shi, Hongdong Li, Xin Yu.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.15407)]

**Nex: Real-time View Synthesis with Neural Basis Expansion.**<br>
*S. Wizadwongsa, P. Phongthawee, J. Yenphraphai, S. Suwajanakorn.*<br>
CVPR 2021 (oral). [[PDF](https://arxiv.org/abs/2103.05606)] [[Project](https://nex-mpi.github.io/)]

**ID-Unet: Iterative Soft and Hard Deformation for View Synthesis.**<br>
*Mingyu Yin, Li Sun, Qingli Li.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.02264)] [[Github](https://github.com/MingyuY/Iterative-view-synthesis)]

**IBRNet: Learning Multi-View Image-Based Rendering.**<br>
*Qianqian Wang, Zhicheng Wang, Kyle Genova, Pratul Srinivasan, Howard Zhou, Jonathan T. Barron, Ricardo Martin-Brualla, Noah Snavely, Thomas Funkhouser.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2102.13090)] [[Project](https://ibrnet.github.io/)]

**SVS: Stable View Synthesis.**<br>
*[Gernot Riegler](https://griegler.github.io/), [Vladlen Koltun](http://vladlen.info).*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2011.07233)] [[Github](https://github.com/intel-isl/StableViewSynthesis)] [[Video](https://youtu.be/gqgXIY09htI)]

**Bowtie Networks: Generative Modeling for Joint Few-Shot Recognition and Novel-View Synthesis.**<br>
*Zhipeng Bao, Yu-Xiong Wang, Martial Hebert.*<br>
ICLR 2021. [[PDF](https://openreview.net/pdf?id=ESG-DMKQKsD)]

**Novel View Synthesis via Depth-guided Skip Connections.**<br>
*Yuxin Hou, Arno Solin, Juho Kannala.*<br>
WACV 2021. [[PDF](https://arxiv.org/abs/2101.01619)] [[Github](https://github.com/AaltoVision/warped-skipconnection-nvs)]

**FVS: Free View Synthesis.**<br>
*[Gernot Riegler](https://griegler.github.io/), [Vladlen Koltun](http://vladlen.info).*<br>
ECCV 2020. [[PDF](http://vladlen.info/papers/FVS.pdf)]  [[Code&Data](https://github.com/intel-isl/FreeViewSynthesis)]

**Rotationally-Temporally Consistent Novel-View Synthesis of Human Performance Video.**<br> 
*Youngjoong Kwon, Stefano Petrangeli, Dahun Kim, Haoliang Wang, Eunbyung Park, Viswanathan Swaminathan, Henry Fuchs.*<br>
ECCV 2020. [[pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123490375.pdf)] [[Supplement](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123490375-supp.zip)]

**A Recurrent Transformer Network for Novel View Action Synthesis.**<br> 
*Kara Marie Schatz, Erik Quintanilla, Shruti Vyas, Yogesh S Rawat.*<br>
ECCV 2020. [[pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123720409.pdf)] [[Supplement](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123720409-supp.zip)]

**MatryODShka: Real-time 6DoF Video View Synthesis using Multi-Sphere Images.**<br> 
*Benjamin Attal, Selena Ling, Aaron Gokaslan, Christian Richardt, James Tompkin.*<br>
ECCV 2020. [[pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123460426.pdf)] [[Supplement](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123460426-supp.zip)]

**Novel View Synthesis on Unpaired Data by Conditional Deformable Variational Auto-Encoder.**<br> 
*Mingyu Yin, Li Sun, Qingli Li.*<br>
ECCV 2020. [[pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123730086.pdf)] [[Supplement](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123730086-supp.pdf)]

**Deep Multi Depth Panoramas for View Synthesis.**<br>
*Kai-En Lin, Zexiang Xu, Ben Mildenhall, Pratul P. Srinivasan, Yannick Hold-Geoffroy, Stephen DiVerdi, Qi Sun, Kalyan Sunkavalli, Ravi Ramamoorthi.*<br>
ECCV 2020. [[pdf](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123580324.pdf)] [[Supplement](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123580324-supp.zip)]

**Semantic View Synthesis.**</br>
*[Hsin-Ping Huang](https://hhsinping.github.io/), [Hung-Yu Tseng](https://sites.google.com/site/hytseng0509/), [Hsin-Ying Lee](http://vllab.ucmerced.edu/hylee/), [Jia-Bin Huang](https://filebox.ece.vt.edu/~jbhuang/).*</br>
ECCV 2020. [[PDF](hhsinping.github.io/svs/link/paper.pdf)] [[Project](hhsinping.github.io/svs/index.htm)]  

**Deep Multi Depth Panoramas for View Synthesis.**<br>
*Kai-En Lin, Zexiang Xu, Ben Mildenhall, Pratul P. Srinivasan, Yannick Hold-Geoffroy, Stephen DiVerdi, Qi Sun, Kalyan Sunkavalli, Ravi Ramamoorthi.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2008.01815)]

**Unsupervised Continuous Object Representation Networks for Novel View Synthesis.**<br>
*Nicolai Häni, Selim Engin, Jun-Jee Chao, Volkan Isler.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2007.15627)]

**AUTO3D: Novel View Synthesis Through Unsupervisely Learned Variational Viewpoint and Global 3D Representation.**<br>
*Xiaofeng Liu, Tong Che, Yiqun Lu, Chao Yang, Site Li, Jane You.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2007.06620)]

**Novel View Synthesis of Dynamic Scenes with Globally Coherent Depths from a Monocular Camera.**<br>
*Jae Shin Yoon, Kihwan Kim, Orazio Gallo, Hyun Soo Park, Jan Kautz.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2004.01294)]

**Self-Supervised 3D Human Pose Estimation via Part Guided Novel Image Synthesis.**<br>
*Jogendra Nath Kundu, Siddharth Seth, Varun Jampani, Mugalodi Rakesh, R. Venkatesh Babu, Anirban Chakraborty.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2004.04400)]

**IGNOR: Image-guided Neural Object Rendering.**<br>
*Justus Thies, Michael Zollhöfer, Christian Theobalt, Marc Stamminger, [Matthias Nießner](http://niessnerlab.org/publications.html).*<br>
ICLR 2020. arxiv, 26 Nov 2018 (15 Jan 2020). [[PDF](https://arxiv.org/abs/1811.10720)] [[Project](http://niessnerlab.org/projects/thies2020ignor.html)]

**Monocular Neural Image Based Rendering with Continuous View Control.**<br>
*[Xu Chen](https://ait.ethz.ch/people/xu/), [Jie Song](https://ait.ethz.ch/people/song/), Otmar Hilliges.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1901.01880)]

**Extreme View Synthesis.**<br>
*Inchang Choi, Orazio Gallo, Alejandro Troccoli, Min H. Kim, Jan Kautz.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1812.04777)]

**Transformable Bottleneck Networks.**<br>
*Kyle Olszewski, Sergey Tulyakov, Oliver Woodford, Hao Li, Linjie Luo.*<br>
ICCV 2019. [[PDF](http://openaccess.thecvf.com/content_ICCV_2019/papers/Olszewski_Transformable_Bottleneck_Networks_ICCV_2019_paper.pdf)]

**View Independent Generative Adversarial Network for Novel View Synthesis.**<br>
*Xiaogang Xu, Ying-Cong Chen, Jiaya Jia.*<br>
ICCV 2019. [[PDF](http://openaccess.thecvf.com/content_ICCV_2019/papers/Xu_View_Independent_Generative_Adversarial_Network_for_Novel_View_Synthesis_ICCV_2019_paper.pdf)]

**PVA: Pixel-Aligned Volumetric Avatars.**<br>
*Amit Raj, Michael Zollhöfer, Tomas Simon, Jason Saragih, Shunsuke Saito, James Hays, Stephen Lombardi.*<br>
CVPR 2021 [[PDF](https://arxiv.org/pdf/2101.02697.pdf)][[Project](https://volumetric-avatars.github.io/)]

**LLFF: Local Light Field Fusion: Practical View Synthesis with Prescriptive Sampling Guidelines.**<br>
*[Ben Mildenhall](http://people.eecs.berkeley.edu/~bmild/), Pratul Srinivasan, Rodrigo Ortiz-Cayon, Nima Khademi Kalantari, Ravi Ramamoorthi, Ren Ng, Abhishek Kar.*<br>
SIGGRAPH 2019. [[PDF](https://arxiv.org/abs/1905.00889)] [[Project](https://people.eecs.berkeley.edu/~bmild/llff/)] [[Github](https://github.com/Fyusion/LLFF)]

**Neural Volumes: Learning Dynamic Renderable Volumes from Images.**<br>
*Stephen Lombardi, Tomas Simon, Jason Saragih, Gabriel Schwartz, Andreas Lehrmann, Yaser Sheikh.*<br>
SIGGRAPH 2019. [[PDF](https://arxiv.org/abs/1906.07751)] [[Github](https://github.com/facebookresearch/neuralvolumes)]

## Light, Reflectance, Illuminance, and Shade

**Learning to Adapt to Light.**<br>
*Kai-Fu Yang, Cheng Cheng, Shi-Xuan Zhao, Xian-Shi Zhang, Yong-Jie Li.*<br>
arxiv 2022. [[PDF](https://arxiv.org/abs/2202.08098)]

**SIRfyN: Single Image Relighting from your Neighbors.**<br>
*D.A. Forsyth, Anand Bhattad, Pranav Asthana, Yuanyi Zhong, Yuxiong Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.04497)]

**Neural Radiance Fields for Outdoor Scene Relighting.**<br>
*Viktor Rudnev, Mohamed Elgharib, William Smith, Lingjie Liu, Vladislav Golyanik, Christian Theobalt.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2112.05140)] [[Project](https://4dqv.mpi-inf.mpg.de/NeRF-OSR/)]

**Intrinsic Image Transfer for Illumination Manipulation.**<br>
*Junqing Huang, Michael Ruzhansky, Qianying Zhang, Haihui Wang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2107.00704)]

**DSRN: an Efficient Deep Network for Image Relighting.**<br>
*Sourya Dipta Das, Nisarg A. Shah, Saikat Dutta, Himanshu Kumar.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2102.09242)]

**Relightable 3D Head Portraits from a Smartphone Video.**<br>
*[Artem Sevastopolsky](https://seva100.github.io/), Savva Ignatiev, Gonzalo Ferrer, Evgeny Burnaev, Victor Lempitsky.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.09963)] [[Project](https://saic-violet.github.io/relightable-portrait/)] [[Video](https://www.youtube.com/watch?v=qQnNalM9hgY)]

**A Shading-Guided Generative Implicit Model for Shape-Accurate 3D-Aware Image Synthesis.**<br>
*Xingang Pan, Xudong Xu, Chen Change Loy, Christian Theobalt, Bo Dai.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2110.15678)]

**Neural-PIL: Neural Pre-Integrated Lighting for Reflectance Decomposition.**<br>
*[Mark Boss](https://markboss.me), Varun Jampani, Raphael Braun, Ce Liu, Jonathan T. Barron, Hendrik P.A. Lensch.*<br>
NeurIPS 2021. [[PDF](https://arxiv.org/abs/2110.14373)] [[Project](https://markboss.me/publication/2021-neural-pil/)]

**C5: Cross-Camera Convolutional Color Constancy.**<br>
*[Mahmoud Afifi](https://sites.google.com/view/mafifi), Jonathan T. Barron, Chloe LeGendre, Yun-Ta Tsai, Francois Bleibel.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2011.11890)] [[GIthub](https://github.com/mahmoudnafifi/C5)]

**NeLF: Neural Light-transport Field for Portrait View Synthesis and Relighting.**<br>
*[Tiancheng Sun](http://kevinkingo.com/), [Kai-En Lin](https://cseweb.ucsd.edu/~k2lin/), [Sai Bi](https://sai-bi.github.io/), [Zexiang Xu](https://cseweb.ucsd.edu/~zex014/), [Ravi Ramamoorthi](https://cseweb.ucsd.edu/~ravir/).*<br>
EGSR 2021. [[PDF](https://arxiv.org/abs/2107.12351)] [[Project](http://cseweb.ucsd.edu/~viscomp/projects/EGSR21NeLF/)]

**Deep Portrait Lighting Enhancement with 3D Guidance.**<br>
*Fangzhou Han, Can Wang, Hao Du, Jing Liao.*<br>
CGF 2021. [[PDF](https://arxiv.org/abs/2108.02121)] [[Project](https://cassiepython.github.io/egsr/index.html)]

**Total Relighting: Learning to Relight Portraits for Background Replacement.**<br>
*Rohit Pandey, Sergio Orts-Escolano, Chloe LeGendre, Christian Haene, Sofien Bouaziz, Christoph Rhemann, Paul Debevec, and Sean Fanello.*<br>
TOG 2021. [[PDF](https://augmentedperception.github.io/total_relighting/total_relighting_paper.pdf)] [[Project](https://augmentedperception.github.io/total_relighting/)]

**Deep Relightable Appearance Models for Animatable Faces.**<br>
*[Sai Bi](https://sai-bi.github.io/), Stephen Lombardi*, Shunsuke Saito*, Tomas Simon, Shih-En Wei, Kevyn McPhail, Ravi Ramamoorthi, Yaser Sheikh, Jason Saragih.*<br>
TOG 2021. [[PDF](https://drive.google.com/file/d/11cj0mdPlpO6_c1rfTeGp7I7j5mu7vtYf/view?usp=sharing)] [[Project](https://cseweb.ucsd.edu/~bisai/project/sig21_avatar/index.html)]

**Neural Light Transport for Relighting and View Synthesis.**<br>
*Xiuming Zhang, Sean Fanello, Yun-Ta Tsai, Tiancheng Sun, Tianfan Xue, Rohit Pandey, Sergio Orts-Escolano, Philip Davidson, Christoph Rhemann, Paul Debevec, Jonathan T. Barron, Ravi Ramamoorthi, William T. Freeman.*<br>
TOG 2021. [[PDF](https://arxiv.org/abs/2008.03806)] [[Project](http://nlt.csail.mit.edu/)]

**Deferred Neural Lighting: Free-viewpoint Relighting from Unstructured Photographs.**<br>
*[Duan Gao](https://gao-duan.github.io/), [Guojun Chen](https://www.microsoft.com/en-us/research/people/guoch/), [Yue Dong](http://yuedong.shading.me/), [Pieter Peers](http://www.cs.wm.edu/~ppeers/), [Kun Xu](https://cg.cs.tsinghua.edu.cn/people/~kun/), [Xin Tong](http://www.xtong.info/).*<br>
TOG 2020. [[PDF](https://gao-duan.github.io/publications/neuralrelighting/DeferredNeuralLighting.pdf)]

**Learning Illumination from Diverse Portraits.**<br>
*Chloe LeGendre, Wan-Chun Ma, Rohit Pandey, Sean Fanello, Christoph Rhemann, Jason Dourgarian, Jay Busch, Paul Debevec.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2008.02396)]

**Light Stage Super-Resolution: Continuous High-Frequency Relighting.**<br>
*Tiancheng Sun, Zexiang Xu, Xiuming Zhang, Sean Fanello, Christoph Rhemann, Paul Debevec, Yun-Ta Tsai, Jonathan T. Barron, Ravi Ramamoorthi.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2010.08888)]

**NuI-Go: Recursive Non-Local Encoder-Decoder Network for Retinal Image Non-Uniform Illumination Removal.**<br>
*Chongyi Li, Huazhu Fu, Runmin Cong, Zechao Li, Qianqian Xu.*<br>
ACM MM 2020. [[PDF](https://arxiv.org/abs/2008.02984)]

**Learning to Factorize and Relight a City.**<br>
*Andrew Liu, Shiry Ginosar, Tinghui Zhou, Alexei A. Efros, Noah Snavely.*<br>
ECCV 2020. [[PDF](https://arxiv.org/abs/2008.02796)] [[Project](http://factorize-a-city.github.io/)]

**Object-based Illumination Estimation with Rendering-aware Neural Networks.**<br>
*Xin Wei, Guojun Chen, Yue Dong, Stephen Lin, Xin Tong.*<br>
ECCV 2200. [[PDF](https://arxiv.org/abs/2008.02514)]

**Enlighten Me: Importance of Brightness and Shadow for Character Emotion and Appeal.**<br>
*Pisut Wisessing, Katja Zibrek, Douglas W. Cunningham, John Dingliana, Rachel McDonnell.*<br>
TOG 2020. [[PDF](https://dl.acm.org/doi/fullHtml/10.1145/3383195)]

**Portrait Shadow Manipulation.**<br>
*[Xuaner Cecilia Zhang](https://people.eecs.berkeley.edu/~cecilia77/), J onathan T. Barron, Yun-Ta Tsai, Rohit Pandey, Xiuming Zhang, Ren Ng, David E. Jacobs.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2005.08925)] [[Project](https://people.eecs.berkeley.edu/~cecilia77/project-pages/portrait)]

**Generating Digital Painting Lighting Effects via RGB-space Geometry.**<br>
*Lvmin Zhang, Edgar Simo-Serra, Yi Ji, and Chunping Liu.*<br>
TOG 2020. [[Priject](https://lllyasviel.github.io/PaintingLight/)] [[Github](https://github.com/lllyasviel/PaintingLight)]

**Single Image Portrait Relighting.**<br>
*[Tiancheng Sun](http://kevinkingo.com/), Jonathan T. Barron, Yun-Ta Tsai, Zexiang Xu, Xueming Yu, Graham Fyffe, Christoph Rhemann, Jay Busch, Paul Debevec, [Ravi Ramamoorthi](https://cseweb.ucsd.edu/~ravir/).*<br> 
TOG 2019. [[PDF](https://arxiv.org/abs/1905.00824)]

**Multi-view Relighting using a Geometry-Aware Network.**<br>
*[Julien Philip](https://www-sop.inria.fr/members/Julien.Philip/), [Michael Gharbi](https://research.adobe.com/person/michael-gharbi/), [Tinghui Zhou](https://people.eecs.berkeley.edu/~tinghuiz/), [Alexei (Alyosha) Efros](https://people.eecs.berkeley.edu/~efros/), [George Drettakis](http://www-sop.inria.fr/members/George.Drettakis/).*<br>
TOG 2019. [[PDF](https://repo-sam.inria.fr/fungraph/deep-relighting/)]

**Lighthouse: Predicting Lighting Volumes for Spatially-Coherent Illumination.**<br>
*Pratul P. Srinivasan, Ben Mildenhall, Matthew Tancik, Jonathan T. Barron, Richard Tucker, Noah Snavely.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2003.08367)] [GitHub](https://github.com/pratulsrinivasan/lighthouse)] [[Project](https://people.eecs.berkeley.edu/~pratul/lighthouse/)]

**Deep 3D Capture: Geometry and Reflectance from Sparse Multi-View Images.**<br>
*Sai Bi, Zexiang Xu, Kalyan Sunkavalli, David Kriegman, Ravi Ramamoorthi.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2003.12642)]

**DNR: A Neural Rendering Framework for Free-Viewpoint Relighting.**<br>
*Zhang Chen, Anpei Chen, Guli Zhang, Chengyuan Wang, Yu Ji, Kiriakos N. Kutulakos, Jingyi Yu.*<br>
CVPR 2020. [[PDF](https://arxiv.org/pdf/1911.11530v1.pdf)]

**Learning to Shade Hand-drawn Sketches.**<br>
*Qingyuan Zheng, Zhuoru Li, Adam Bargteil.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2002.11812)]

**Deep Single-Image Portrait Relighting.**<br>
*Hao Zhou, Sunil Hadap, Kalyan Sunkavalli, David W. Jacobs.*<br>
ICCV 2019. [[PDF](https://zhhoper.github.io/paper/zhou_ICCV2019_DPR.pdf)] [[Github](https://github.com/zhhoper/DPR)] [[Project](https://zhhoper.github.io/dpr.html)] [[DPR Dataset](https://drive.google.com/drive/folders/10luekF8vV5vo2GFYPRCe9Rm2Xy2DwHkT?usp=sharing)]

**Deep Parametric Indoor Lighting Estimation.**<br>
*Marc-André Gardner, Yannick Hold-Geoffroy, Kalyan Sunkavalli, Christian Gagné, and Jean-François Lalonde.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1910.08812)] [[Supplementary material](https://lvsn.github.io/deepparametric/supplementary/index.html)] [[Laval Indoor HDR Database](http://indoor.hdrdb.com/) and [Depth](http://indoordepth.hdrdb.com/)] [[Project](https://lvsn.github.io/deepparametric/)] 

**GLoSH: Global-Local Spherical Harmonics for Intrinsic Image Decomposition.**<br>
*[Hao Zhou](http://zhhoper.github.io), Xiang Yu, David W Jacobs.*<br>
ICCV 2019. [[PDF](https://zhhoper.github.io/paper/zhou_ICCV2019_IID.pdf)] [[Supplement](https://zhhoper.github.io/paper/zhou_ICCV_2019_IID_sup.pdf)] [[Poster](https://zhhoper.github.io/poster/Poster_ICCV_2019_IID.pdf)] [[Spherical Harmonic Tools](shtools.github.io/SHTOOLS)]


**Fast Spatially-Varying Indoor Lighting Estimation.**<br>
*Mathieu Garon, Kalyan Sunkavalli, Sunil Hadap, Nathan Carr, [Jean-François Lalonde](http://www.jflalonde.ca/).*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1906.03799)] [[Supplementary material](https://lvsn.github.io/fastindoorlight/supplementary/index.html)] [[Project](https://lvsn.github.io/fastindoorlight/)] [[Lavel Indoor Spatially Varying HDR Dataset / 79 HDR Light Probes](http://indoorsv.hdrdb.com/)]

**Neural Illumination: Lighting Prediction for Indoor Environments.**<br>
*Shuran Song and Thomas Funkhouser.*<br>
CVPR 2019. [[PDF](https://illumination.cs.princeton.edu/paper.pdf)] [[Project](https://illumination.cs.princeton.edu/)]

**SfSNet: Learning Shape, Reflectance and llluminance of Faces in the Wild.**<br>
*Soumyadip Sengupta, Angjoo Kanazawa, Carlos D. Castillo, David W. Jacobs.*<br>
CVPR 2018. [[Project](https://senguptaumd.github.io/SfSNet/)] [[PDF](https://arxiv.org/abs/1703.10131)] [[Github](https://github.com/matansel/pix2vertex)]

**Illumination Decomposition for Photograph with Multiple Light Sources.**<br>
*Ling Zhang, Qingan Yan, Zheng Liu, Hua Zou, Chunxia Xiao.*<br>
TIP 2017. [[PDF](https://yanqingan.github.io/docs/tip17_illumination.pdf)] [[Github](https://github.com/yanqingan/Illumination_Decomposition)]

**Learning to Predict Indoor Illumination from a Single Image.**<br>
*Marc-André Gardner, [Kalyan Sunkavalli](https://research.adobe.com/person/kalyan-sunkavalli/), [Ersin Yumer](https://research.adobe.com/person/ersin-yumer/), [Xiaohui Shen](https://research.adobe.com/person/xiaohui-shen/), Emiliano Gambaretto, [Christian Gagné](http://vision.gel.ulaval.ca/~cgagne/), and [Jean-François Lalonde](http://vision.gel.ulaval.ca/~jflalonde/).*<br>
TOG 2017. [[PDF](https://arxiv.org/abs/1704.00090)] [[Dataset](http://indoor.hdrdb.com/)] [[Homepage](vision.gel.ulaval.ca/~jflalonde/projects/deepIndoorLight)]

**Occlusion-aware 3D Morphable Models and an Illumination Prior for Face Image Analysis.**<br>
*Bernhard Egger, Sandro Schoenborn, Andreas Schneider, Adam Kortylewski, Andreas Morel-Forster, Clemens Blumer and Thomas Vetter.*<br>
IJCV 2018. [[BIP Dataset](https://gravis.dmi.unibas.ch/PMM/data/bip/)] [[PDF](http://gravis.dmi.unibas.ch/publications/2018/2018_Egger_IJCV.pdf)]

**Deep Shading: Convolutional Neural Networks for Screen-Space Shading.**<br>
*Oliver Nalbach, Elena Arabadzhiyska, Dushyant Mehta, Hans-Peter Seidel, Tobias Ritschel.*<br>
CFG 2016. [[PDF](https://arxiv.org/abs/1603.06078)] [[Github](https://github.com/marcelsan/DeepShading)]

## Dubbing and Talking-Head Animation

**DFA-NeRF: Personalized Talking Head Generation via Disentangled Face Attributes Neural Rendering.**<br>
*Shunyu Yao, RuiZhe Zhong, Yichao Yan, Guangtao Zhai, Xiaokang Yang.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2201.00791)]

**FaceFormer: Speech-Driven 3D Facial Animation with Transformers.**<br>
*Yingruo Fan, Zhaojiang Lin, Jun Saito, Wenping Wang, Taku Komura.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2112.05329)] 

**Large-Scale Multilingual Audio Visual Dubbing.**<br>
*Yi Yang, Brendan Shillingford, Yannis Assael, Miaosen Wang, Wendi Liu, Yutian Chen, Yu Zhang, Eren Sezener, Luis C. Cobo, Misha Denil, Yusuf Aytar, Nando de Freitas.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2011.03530)] [[Video](https://www.youtube.com/playlist?list=PLSi232j2ZA6_1Exhof5vndzyfbxAhhEs5)]

**EBT: Everybody's Talkin': Let Me Talk as You Want.**<br>
*Linsen Song, [Wayne Wu](http://wywu.github.io/), Chen Qian, [Ran He](https://scholar.google.com/citations?user=ayrg9AUAAAAJ&hl=en), Chen Change Loy.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2001.05201)] [[Project](https://wywu.github.io/projects/EBT/EBT.html)]

**Audio-driven Talking Face Video Generation with Learning-based Personalized Head Pose.**<br>
*Ran Yi, Zipeng Ye, Juyong Zhang, Hujun Bao, Yong-Jin Liu.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2002.10137)] [[Github](https://github.com/yiranran/Audio-driven-TalkingFace-HeadPose)]

**Speech Driven Talking Face Generation from a Single Image and an Emotion Condition.**<br>
*Sefik Emre Eskimez, You Zhang, Zhiyao Duan.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2008.03592)]

**SAFA: Structure Aware Face Animation.**<br>
*Qiulin Wang, Lu Zhang, Bo Li.*<br>
3DV 2021. [[PDF](https://arxiv.org/abs/2111.04928)] [[Github](https://github.com/Qiulin-W/SAFA)]

**One-shot Talking Face Generation from Single-speaker Audio-Visual Correlation Learning.**<br>
*Suzhen Wang, Lincheng Li, Yu Ding, Xin Yu.*<br>
AAAI 2022. [[PDF](https://arxiv.org/abs/2112.02749)]

**Talking Head Generation with Audio and Speech Related Facial Action Units.**<br>
*Sen Chen, Zhilei Liu, Jiaxing Liu, Zhengxiang Yan, Longbiao Wang.*<br>
BMVC 2021. [[PDF](https://arxiv.org/abs/2110.09951)]

**Live Speech Portraits: Real-Time Photorealistic Talking-Head Animation.**<br>
*Yuanxun Lu, Jinxiang Chai, Xun Cao.*<br>
SIGGRAPH Asia 2021. [[PDF](https://arxiv.org/abs/2109.10595)]

**DECA: Learning an Animatable Detailed 3D Face Model from In-The-Wild Images.**<br>
*Yao Feng, Haiwen Feng, Michael J. Black, Timo Bolkart.*<br>
SIGGRAPH 2021. [[PDF](https://arxiv.org/abs/2012.04012)] [[Github](https://github.com/YadiraF/DECA)]

**Towards Realistic Visual Dubbing with Heterogeneous Sources.**<br>
*Tianyi Xie, Liucheng Liao, Cheng Bi, Benlai Tang, Xiang Yin, Jianfei Yang, Mingjie Wang, Jiali Yao, Yang Zhang, Zejun Ma.*<br>
ACM MM 2021. [[PDF](https://arxiv.org/abs/2201.06260)]

**Learned Spatial Representations for Few-Shot Talking-Head Synthesis.**<br>
*Moustafa Meshry, Saksham Suri, Larry S. Davis, Abhinav Shrivastava.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Meshry_Learned_Spatial_Representations_for_Few-Shot_Talking-Head_Synthesis_ICCV_2021_paper.html)]

**The Right To Talk: An Audio-Visual Transformer Approach.**<br>
*Thanh-Dat Truong, Chi Nhan Duong, The De Vu, Hoang Anh Pham, Bhiksha Raj, Ngan Le, Khoa Luu.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Truong_The_Right_To_Talk_An_Audio-Visual_Transformer_Approach_ICCV_2021_paper.html)]

**Speech Drives Templates: Co-Speech Gesture Synthesis With Learned Templates.**<br>
*Shenhan Qian, Zhi Tu, Yihao Zhi, Wen Liu, Shenghua Gao.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Qian_Speech_Drives_Templates_Co-Speech_Gesture_Synthesis_With_Learned_Templates_ICCV_2021_paper.html)]

**AD-NeRF: Audio Driven Neural Radiance Fields for Talking Head Synthesis.**<br>
*[Yudong Guo](https://yudongguo.github.io/), [Keyu Chen](http://kychern.github.io/), Sen Liang, [Yongjin Liu](https://cg.cs.tsinghua.edu.cn/people/~Yongjin/Yongjin.htm), [Hujun Bao](http://www.cad.zju.edu.cn/bao/), [Juyong Zhang](http://staff.ustc.edu.cn/~juyong/).*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2103.11078)] [[Project](https://yudongguo.github.io/ADNeRF/)] [[Video](https://www.youtube.com/watch?v=TQO2EBYXLyU)]

**FACIAL: Synthesizing Dynamic Talking Face with Implicit Attribute Learning.**<br>
*Chenxu Zhang, Yifan Zhao, Yifei Huang, Ming Zeng, Saifeng Ni, Madhukar Budagavi, Xiaohu Guo.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2108.07938)]

**MeshTalk: 3D Face Animation from Speech using Cross-Modality Disentanglement.**<br>
*[Alexander Richard](https://alexanderrichard.github.io/), Michael Zollhoefer, Yandong Wen, Fernando de la Torre, Yaser Sheikh.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2104.08223)] [[Video](https://research.fb.com/wp-content/uploads/2021/04/mesh_talk.mp4)]

**HeadGAN: Video-and-Audio-Driven Talking Head Synthesis.**<br>
*Michail Christos Doukas, Stefanos Zafeiriou, Viktoriia Sharmanska.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2012.08261)]

**Audio2Head: Audio-driven One-shot Talking-head Generation with Natural Head Motion.**<br>
*Suzhen Wang, Lincheng Li, Yu Ding, Changjie Fan, Xin Yu.*<br>
IJCAI 2021. [[PDF](https://arxiv.org/abs/2107.09293)]

**Imitating Arbitrary Talking Style for Realistic Audio-Driven Talking Face Synthesis.**<br>
*Haozhe Wu, Jia Jia, Haoyu Wang, Yishun Dou, Chao Duan, Qingshan Deng.*<br>
ACM MM 2021. [[PDF](https://hcsi.cs.tsinghua.edu.cn/Paper/Paper21/MM21-WUHAOZHE.pdf)] [[GIthub](https://github.com/wuhaozhe/style_avatar)]

**LipSync3D: Data-Efficient Learning of Personalized 3D Talking Faces from Video using Pose and Lighting Normalization.**<br>
*Avisek Lahiri, Vivek Kwatra, Christian Frueh, John Lewis, Chris Bregler.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2106.04185)]

**Pose-Controllable Talking Face Generation by Implicitly Modularized Audio-Visual Representation.**<br> 
*[Hang Zhou](https://hangz-nju-cuhk.github.io/), Yasheng Sun, [Wayne Wu](https://wywu.github.io/), Chen Change Loy, Xiaogang Wang, Ziwei Liu.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2104.11116)] [[Project](https://hangz-nju-cuhk.github.io/)] [[Github](https://github.com/Hangz-nju-cuhk/Talking-Face_PC-AVS)]

**Everything's Talkin': Pareidolia Face Reenactment.**<br>
*Linsen Song, [Wayne Wu](https://wywu.github.io), Chaoyou Fu, Chen Qian, Chen Change Loy, Ran He.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2104.03061)] [[Project](https://wywu.github.io/projects/ETT/ETT.html)] [[Github](https://github.com/Linsen13/EverythingTalking)]

**One-Shot Free-View Neural Talking-Head Synthesis for Video Conferencing.**<br>
*[Ting-Chun Wang](https://tcwang0509.github.io/), [Arun Mallya](https://arunmallya.github.io/), [Ming-Yu Liu](http://mingyuliu.net/).*<br>
CVPR 2021 (oral). [[PDF](https://arxiv.org/abs/2011.15126)] [[Project](https://nvlabs.github.io/face-vid2vid)]

**MEAD: A Large-scale Audio-visual Dataset for Emotional Talking Face Generation.**<br>
*Kaisiyuan Wang, [Qianyi Wu](https://wuqianyi.top/), Linsen Song, [Zhuoqian Yang](https://yzhq97.github.io/), Wayne Wu, Chen Qian, Ran He, Yu Qiao, Chen Change Loy.*<br>
ECCV 2020. [[PDF](https://wywu.github.io/)] [[Project](https://wywu.github.io/projects/MEAD/MEAD.html)] [[Github](https://github.com/uniBruce/Mead)] 

**MakeItTalk: Speaker-Aware Talking-Head Animation.**<br>
*Yang Zhou, Xintong Han, Eli Shechtman, Jose Echevarria, Evangelos Kalogerakis, Dingzeyu Li.*<br>
TOG 2020. [[PDF](https://arxiv.org/abs/2004.12992)] [[Github](https://github.com/adobe-research/MakeItTalk)]

**FLNet: Landmark Driven Fetching and Learning Network for Faithful Talking Facial Animation Synthesis.**<br>
*Kuangxiao Gu, Yuqian Zhou, Thomas Huang.*<br>
AAAI 2020. [[PDF](https://arxiv.org/abs/1911.09224)] [[GitHub](https://github.com/kgu3/FLNet_AAAI2020)]

**Text-based Editing of Talking-head Video.**<br>
*Ohad Fried, Ayush Tewari, Michael Zollhöfer, Adam Finkelstein, Eli Shechtman, Dan B Goldman Kyle Genova, Zeyu Jin, Christian Theobalt,  Maneesh Agrawala.*<br>
TOG 2019. [[PDF](https://www.ohadf.com/projects/text-based-editing/data/text-based-editing.pdf)] [[Project](https://www.ohadf.com/projects/text-based-editing/)]

**ATVGnet: Hierarchical Cross-Modal Talking Face Generationwith Dynamic Pixel-Wise Loss.**<br>
*[Lele Chen](http://www.cs.rochester.edu/u/lchen63/), [Ross K. Maddox](https://www.urmc.rochester.edu/labs/maddox.aspx), [Zhiyao Duan](http://www2.ece.rochester.edu/~zduan/), [Chenliang Xu](https://www.cs.rochester.edu/~cxu22/).*<br>
CVPR 2019. [[PDF](https://arxiv.org/abs/1905.03820)] [[Github](https://github.com/lelechen63/ATVGnet)]

**Talking Face Generation by Adversarially Disentangled Audio-Visual Representation.**<br>
*Hang Zhou, Yu Liu, Ziwei Liu, Ping Luo, Xiaogang Wang.*<br>
AAAI 2019. [[PDF](https://arxiv.org/abs/1807.07860)] [[Github](https://github.com/Hangz-nju-cuhk/Talking-Face-Generation-DAVS)] [[Project](https://liuziwei7.github.io/projects/TalkingFace.html)]

## Motion Transfer, Retargeting, and Reenactment

[[awesome-human-motion](https://github.com/derikon/awesome-human-motion)]

**FSGANv2: Improved Subject Agnostic Face Swapping and Reenactment.**<br>
*Yuval Nirkin, Yosi Keller, Tal Hassner.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2202.12972)]

**Towards Using Clothes Style Transfer for Scenario-aware Person Video Generation.**<br>
*Jingning Xu, benlai Tang, Mingjie Wang, Siyuan Bian, Wenyi Guo, Xiang Yin, Zejun Ma.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2110.11894)] [[Github](https://github.com/XSimba123/demos-of-csf-sa/)]

**Mesh Draping: Parametrization-Free Neural Mesh Transfer.**<br>
*Amir Hertz, Or Perel, Raja Giryes, Olga Sorkine-Hornung, Daniel Cohen-Or.*<br>
arxiv 2021. [[PDF](https://arxiv.org/abs/2110.05433)]

**Self-appearance-aided Differential Evolution for Motion Transfer.**<br>
*Peirong Liu, Rui Wang, Xuefei Cao, Yipin Zhou, Ashish Shah, Maxime Oquab, Camille Couprie, Ser-Nam Lim.*<br>
arxiv 2021. [[PDF](https://arxiv.org/pdf/2110.04658.pdf)]

**Learning Realistic Human Reposing using Cyclic Self-Supervision with 3D Shape, Pose, and Appearance Consistency.**<br>
*Soubhik Sanyal, Alex Vorobiov, Timo Bolkart, Matthew Loper, Betty Mohler, Larry Davis, Javier Romero, Michael J. Black.*<br>
ICCV 2021. [[PDF](https://arxiv.org/pdf/2110.05458.pdf)] 

**Contact-Aware Retargeting of Skinned Motion.**<br>
*Ruben Villegas, Duygu Ceylan, Aaron Hertzmann, Jimei Yang, Jun Saito.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Villegas_Contact-Aware_Retargeting_of_Skinned_Motion_ICCV_2021_paper.html)]

**PIRenderer: Controllable Portrait Image Generation via Semantic Neural Rendering.**<br>
*Yurui Ren, Ge Li, Yuanqi Chen, Thomas H. Li, Shan Liu.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2109.08379)]

**Intrinsic-Extrinsic Preserved GANs for Unsupervised 3D Pose Transfer.**<br>
*[Haoyu Chen](https://www.oulu.fi/university/researcher/haoyu-chen), Hao Tang, Henglin Shi, Wei Peng, Nicu Sebe, Guoying Zhao.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2108.07520)] [[Github](https://github.com/mikecheninoulu/Unsupervised_IEPGAN)]

*Dressing in Order: Recurrent Person Image Generation for Pose Transfer, Virtual Try-On and Outfit Editing.*<br>
*Aiyu Cui, Daniel McKee, Svetlana Lazebnik.*<br>
ICCV 2021. [[PDF](https://openaccess.thecvf.com/content/ICCV2021/html/Cui_Dressing_in_Order_Recurrent_Person_Image_Generation_for_Pose_Transfer_ICCV_2021_paper.html)]

**HeadGAN: One-shot Neural Head Synthesis and Editing.**<br>
*Michail Christos Doukas, Stefanos Zafeiriou, Viktoriia Sharmanska.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2012.08261)]

**Contact-Aware Retargeting of Skinned Motion.**<br>
*Ruben Villegas, Duygu Ceylan, Aaron Hertzmann, Jimei Yang, Jun Saito.*<br>
ICCV 2021. [[PDF](https://arxiv.org/abs/2109.07431)]

**SimPoE: Simulated Character Control for 3D Human Pose Estimation.**<br>
*Ye Yuan, Shih-En Wei, Tomas Simon, Kris Kitani, Jason Saragih.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2104.00683)] [[Project](https://www.ye-yuan.com/simpoe/)]

**Few-Shot Human Motion Transfer by Personalized Geometry and Texture Modeling.**<br>
*Zhichao Huang, Xintong Han, Jia Xu, Tong Zhang.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2103.14338)]

**Single-Shot Freestyle Dance Reenactment.**<br>
*Oren Nuriel, Oron Ashual, Lior Wolf.*<br>
CVPR 2021. [[PDF](https://arxiv.org/abs/2012.01158)]

**Local Motion Phases for Learning Multi-Contact Character Movements.**<br>
*[Sebastian Starke](https://www.linkedin.com/in/sebastian-starke-b281a6148/), Yiwei Zhao, Taku Komura, Kazi Zaman.*<br>
Siggraph 2020. [[PDF](https://github.com/sebastianstarke/AI4Animation/blob/master/Media/SIGGRAPH_2020/Paper.pdf)] [[AI4Animation](https://github.com/sebastianstarke/AI4Animation)]

**Neural State Machine for Character-Scene Interactions.**<br>
*Sebastian Starke, He Zhang, Taku Komura, Jun Saito.*<br>
TOG 2019. [[PDF](https://github.com/sebastianstarke/AI4Animation/blob/master/Media/SIGGRAPH_Asia_2019/Paper.pdf)] [[Code & Data](https://github.com/sebastianstarke/AI4Animation/blob/master/AI4Animation/SIGGRAPH_Asia_2019)]

**High-Fidelity Neural Human Motion Transfer from Monocular Video.**<br>
*Moritz Kappel, Vladislav Golyanik, Mohamed Elgharib, Jann-Ole Henningson, Hans-Peter Seidel, Susana Castillo, Christian Theobalt, Marcus Magnor.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2012.10974)] [[Project](https://graphics.tu-bs.de/publications/kappel2020high-fidelity)] 

**Image Animation with Perturbed Masks.**<br>
*Yoav Shalev, Lior Wolf.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2011.06922)] [[Github](https://github.com/itsyoavshalev/Image-Animation-with-Perturbed-Masks)]

**Photorealistic Audio-driven Video Portraits.**<br>
*Xin Wen, Miao Wang, Christian Richardt, Ze-Yin Chen, Shi-Min Hu.*<br>
TVCG (ISMAR 2020). [[PDF](https://richardt.name/publications/audio-dvp/AudioDVP-WenEtAl-TVCG2020.pdf)] [[Github](https://github.com/xinwen-cs/AudioDVP)] [[Project](https://richardt.name/publications/audio-dvp/)]

**FACEGAN: Facial Attribute Controllable rEenactment GAN.**<br>
*Soumya Tripathy, Juho Kannala, Esa Rahtu.*<br>
WACV 2021. [[PDF](https://arxiv.org/abs/2011.04439)]

**Generative Adversarial Networks in Human Emotion Synthesis:A Review.**<br>
*Noushin Hajarolasvadi, Miguel Arjona Ramírez, Hasan Demirel.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2010.15075)]

**Mesh Guided One-shot Face Reenactment using Graph Convolutional Networks.**<br>
*Guangming Yao, Yi Yuan, Tianjia Shao, Kun Zhou.*<br>
ACM MM 2020. [[PDF](https://arxiv.org/abs/2008.07783)]

**Learning to Generate Diverse Dance Motions with Transformer.**<br>
*Jiaman Li, Yihang Yin, Hang Chu, Yi Zhou, Tingwu Wang, Sanja Fidler, Hao Li.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2008.08171)]

**Action2Motion: Conditioned Generation of 3D Human Motions.**<br>
*Chuan Guo, Xinxin Zuo, Sen Wang, Shihao Zou, Qingyao Sun, Annan Deng, Minglun Gong, Li Cheng.*<br>
ACM MultiMedia 2020. [[PDF](https://arxiv.org/abs/2007.15240)]

**ReenactNet: Real-time Full Head Reenactment.**<br>
*Mohammad Rami Koujan, Michail Christos Doukas, Anastasios Roussos, Stefanos Zafeiriou.*<br>
FG 2020. [[PDF](https://arxiv.org/abs/2006.10500)]

**FaR-GAN for One-Shot Face Reenactment.**<br>
*Hanxiang Hao, Sriram Baireddy, Amy R. Reibman, Edward J. Delp.*<br>
AI for content creation workshop at CVPR 2020. [[PDF](https://arxiv.org/abs/2005.06402)]

**Skeleton-Aware Networks for Deep Motion Retargeting.**<br>
*Kfir Aberman, Peizhuo Li, Dani Lischinski, Olga Sorkine-Hornung, Daniel Cohen-Or, Baoquan Chen.*<br>
SIGGRAPH 2020. [[Github](https://github.com/DeepMotionEditing/deep-motion-editing)] [[Project](https://deepmotionediting.github.io/retargeting)]

**Unpaired Motion Style Transfer from Video to Animation.**<br>
*Kfir Aberman, Yijia Weng, Dani Lischinski, Daniel Cohen-Or, Baoquan Chen.*<br>
SIGGRAPH 2020. [[Github](https://github.com/DeepMotionEditing/deep-motion-editing)] [[Project](https://deepmotionediting.github.io/style_transfer)]

**LipGAN: Towards Automatic Face-to-Face Translation.**<br>
*Prajwal K R, Rudrabha Mukhopadhyay, Jerin Philip, Abhishek Jha, Vinay Namboodiri, C.V. Jawahar.*<br>
ACM MM 2019. [[PDF](https://arxiv.org/abs/2003.00418v1)] [[Github](https://github.com/Rudrabha/LipGAN)]

**One-Shot Identity-Preserving Portrait Reenactment.**<br>
*Sitao Xiang, Yuming Gu, Pengda Xiang, Mingming He, Koki Nagano, Haiwei Chen, Hao Li.*<br>
arriv, 2020. [[PDF](https://arxiv.org/abs/2004.12452)] 

**Neural Head Reenactment with Latent Pose Descriptors.**<br>
*Egor Burkov, Igor Pasechnik, Artur Grigorev, Victor Lempitsky.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2004.12000)]

**Neural Human Video Rendering by Learning Dynamic Textures and Rendering-to-Video Translation.**<br>
*Lingjie Liu, Weipeng Xu, Marc Habermann, Michael Zollhoefer, Florian Bernard, Hyeongwoo Kim, Wenping Wang, Christian Theobalt.*<br>
arriv, 2020. [[PDF](https://arxiv.org/abs/2001.04947v2)]

**StyleRig: Rigging StyleGAN for 3D Control over Portrait Images.**<br>
*A. Tewari, M. Elgharib, G. Bharaj, F. Bernard, H-P. Seidel, P. Perez, M. Zollhöfer, C.Theobalt.*<br>
CVPR 2020. [[PDF](http://gvv.mpi-inf.mpg.de/projects/StyleRig/data/paper.pdf)] [[Project](http://gvv.mpi-inf.mpg.de/projects/StyleRig/)]

**TransMoMo: Invariance-Driven Unsupervised Video Motion Retargeting.**<br>
*Zhuoqian Yang, Wentao Zhu, Wayne Wu, Chen Qian, Qiang Zhou, Bolei Zhou, Chen Change Loy.*<br>
CVPR 2020. [[PDF](https://arxiv.org/abs/2003.14401)] [[Github](https://github.com/yzhq97/transmomo.pytorch)] [[Project](https://yzhq97.github.io/transmomo)]

**Human Motion Transfer from Poses in the Wild.**<br>
*Jian Ren, Menglei Chai, Sergey Tulyakov, Chen Fang, Xiaohui Shen, Jianchao Yang.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2004.03142)]

**First Order Motion Model for Image Animation.**<br>
*[Aliaksandr Siarohin](https://aliaksandrsiarohin.github.io/), [Stéphane Lathuilière](http://stelat.eu/), [Sergey Tulyakov](http://stulyakov.com/), [Elisa Ricci](http://elisaricci.eu/), [Nicu Sebe](http://disi.unitn.it/~sebe/).*<br>
NeurIPS 2019. [[PDF](http://papers.nips.cc/paper/8935-first-order-motion-model-for-image-animation)] [[Project](https://aliaksandrsiarohin.github.io/first-order-model-website)] [[Github](https://github.com/AliaksandrSiarohin/first-order-model)]

**Neural Human Video Rendering: Joint Learning of Dynamic Textures and Rendering-to-Video Translation.**<br>
*Lingjie Liu, Weipeng Xu, Marc Habermann, Michael Zollhoefer, Florian Bernard, Hyeongwoo Kim, Wenping Wang, Christian Theobalt.*<br>
arxiv 2020. [[PDF](https://arxiv.org/abs/2001.04947)]

**Deferred Neural Rendering: Image Synthesis using Neural.**<br>
*Justus Thies, Michael Zollhöfer, Matthias Nießner.*<br>
SIGGRAPH 2019. [[PDF](https://arxiv.org/abs/1904.12356)]

**LOGAN: Unpaired Shape Transform in Latent Overcomplete Space.**<br>
*Kangxue Yin, Zhiqin Chen, Hui Huang, Daniel Cohen-Or, Hao Zhang.*<br>
SIGGRAPH Asia, 2019. [[PDF](https://arxiv.org/pdf/1903.10170.pdf)]

**Liquid Warping GAN: A Unified Framework for Human Motion Imitation, Appearance Transfer and Novel View Synthesis.**<br>
*Wen Liu, Zhixin Piao, Jie Min, Wenhan Luo, Lin Ma, Shenghua Gao.*<br>
ICCV 2019. [[PDF](https://arxiv.org/abs/1909.12224)] [[HomePage]( https://motionretargeting2d.github.io)]   [[Github](https://github.com/svip-lab/impersonator)]. 

**Learning Character-Agnostic Motion for Motion Retargeting in 2D.**<br>
*Kfir Aberman, Rundi Wu, Dani Lischinski, Baoquan Chen, Daniel Cohen-Or.*<br>
SIGGRAPH 2019. [[PDF](https://arxiv.org/abs/1905.01680)] [[Github](https://github.com/ChrisWu1997/2D-Motion-Retargeting)] [[Project](https://motionretargeting2d.github.io/)]

**Progressive Pose Attention Transfer for Person Image Generation.**<br>
*Zhen Zhu, Tengteng Huang, Baoguang Shi, Miao Yu, Bofei Wang, Xiang Bai.*<br>
CVPR 2019. [[Project](https://github.com/tengteng95/Pose-Transfer)] [[PDF](https://arxiv.org/abs/1904.03349)]

**Textured Neural Avatars.**<br>
*Aliaksandra Shysheya, Egor Zakharov, Kara-Ali Aliev, Renat Bashirov, Egor Burkov, Karim Iskakov, Aleksei Ivakhnenko, Yury Malkov, Igor Pasechnik, Dmitry Ulyanov, Alexander Vakhitov, Victor Lempitsky.*<br>
CVPR 2019 (oral). [[PDF](https://arxiv.org/abs/1905.08776)] [[Project](https://saic-violet.github.io/texturedavatar/)]

**Appearance Composing GAN: A General Method for Appearance-Controllable Human Video Motion Transfer.**<br>
*Dongxu Wei, Haibin Shen, Kejie Huang.*<br>
arxiv 2019. [[PDF](https://arxiv.org/abs/1911.10672)]

**ANR: Articulated Neural Rendering of Virtual Avatars**<br>
*Amit Raj, Julian Tanke, James Hays, Minh Vo, Carsten Stoll, Christoph Lassner.*<br>
CVPR 2021 [[PDF](https://arxiv.org/pdf/2012.12890.pdf)][[Project](https://anr-avatars.github.io/)]

## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
