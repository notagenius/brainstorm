# **off-topic**
My Personal working livestream is online every working day. it is not serious, can only be used as status and availablity check: [https://www.twitch.tv/thatwolfiefeeling](https://www.twitch.tv/thatwolfiefeeling)

# Paper 1: NeRF

- **Field**: Novel View Synthesis ∈ Neural Rendering
- **Spatial Representation**: 
1. explicit (triangle meshes, point cloud, voxelgrid, reconstruction process is the heaviest)
2. implicit (neural network as one whole scene representation)
3. hybrid
4. note: explicit one often using convolutional networks, and implicit one with MLP
- **Rendering**: 
1. traditional (rasterization, ray tracing, path tracing)
2. edgy (volumetric ray, sphere tracing)
3. special (alpha blending)


- **Paper Highlights**
1. neural becomes a presenting of a scene
2. volume rendering with radiance fields and volume density, differentiable
3. positional encoding with fourier transformation
4. hierarchical volume sampling, making sampling more close to continuous

- **Pros:**
1. images and camera parameters as groundtruth, no 3d models needed.
2. high quality rendering
3. simplicity
4. memory-friendly, network size is small

- **Cons:**
1. one scene per training, generalization is bad
2. illumination has to be the same
3. rendering (inference) is slow

- **Datasets**
1. [DeepVoxels dataset](https://drive.google.com/drive/folders/1ScsRlnzy9Bd_n-xw83SP-0t548v63mPH)
2. [their own dataset](https://github.com/bmild/nerf)

- **Thoughts**
1. implicit representation could be found in earlier work like DeepSDF 
1. cannot find classic definition of "Radiance Field", but it is almost identical to [this 2012 blog post](https://www.reedbeta.com/blog/the-radiance-field/#sufficient-conditions), while rendering equations is linear on the space of radiance fields, it makes MLP a perfect sense.
2. 5D field is identical to light field space
3. volume density δ: some researchers have interpreted this as opacity. I think it's incorrect. Based on the definition (the pobability it get stopped from near to far), it is depth, which is replaced the concept of scalars with probabilities
4. if camera parameters are missing, an estimation can be gained by [structure-from-motion](https://colmap.github.io/) 
5. The use of deep learning places emphasis on the differentiable and continuous properties than traditional computer graphics.

- **Cluelessness**
1. positional encoding: it is fourier transformation. don't understand why switching coordinates to frequency domain, keeping the images in space domain can do the charm. no detailed discussion provided in paper.
2. don't know its ability of handling transparent objects, no samples or any mentions. hand-on tests are needed.
3. while CG works involving optics, physics, radiometry and more, I have an impression that a same thing can have different terms, or what intuitively look similar but with blurry definitions. e.g. irrandience / spectral intensity / intensity of light / radiant intensity / radiant flux / radiant emittance. so in writing if we need to choose rigorous, consistent terminology with clearly addressed definition or we carrying linguistic diversity.

- **Extented Works**
1. GRAF（Generative Radiance Fields）, with GAN
2. GIRAFFE (CVPR 2021), fancy composition

- **Related Literature (briefly-readed)**

1. [UCSB CG Lecture](https://sites.cs.ucsb.edu/~lingqi/teaching/games101.html)

2. [Blog: Rendering Equation in radiance fields](https://www.reedbeta.com/blog/the-radiance-field/#sufficient-conditions)

3. [Advances in Neural Rendering SIGGRAPH 2021 Course](https://www.youtube.com/watch?v=otly9jcZ0Jg)

4. [State of the Art on Neural Rendering](State of the Art on Neural Rendering)

5. [Differentiable Rendering: A Survey](Differentiable Rendering: A Survey)

6. [Neural Volume Rendering: NeRF And Beyond](Neural Volume Rendering: NeRF And Beyond)

7. [THE RENDERING EQUATION](THE RENDERING EQUATION)

8. [DeepSDF: Learning Continuous Signed Distance Functions
for Shape Representation](DeepSDF: Learning Continuous Signed Distance Functions
for Shape Representation)

9. [GRAF: Generative Radiance Fields
for 3D-Aware Image Synthesis](GRAF: Generative Radiance Fields
for 3D-Aware Image Synthesis)

10. [GIRAFFE (CVPR 2021), fancy composition]

11. [GIRAFFE: Representing Scenes As Compositional Generative Neural Feature Fields]

# Paper 2: WoodPixel
- **Off-Topic**
1. I used to make a extension for blender as ["virtual laser-cutter"](https://github.com/notagenius/virtual_laser_cutter), it is also with customized texture. can make a virtual cut and automatic assembly with blender scripts I believe.

![vitural laser cutter](https://github.com/notagenius/virtual_laser_cutter/blob/master/doc/side_view_render.png)

- **code**
1. compiled c++ dependency
2. don't know how to run training, no data. also missing insturction

# Paper 3: Deep Non-Line-Of-Sight Reconstruction



