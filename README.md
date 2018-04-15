<center><h2>Adaptive Multigrid Solvers (Version 10.00)</h2></center>
<center>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html#LINKS">links</a>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html#EXECUTABLES">executables</a>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html#USAGE">usage</a>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html#CHANGES">changes</a>
</center>
<hr>
This code-base was born from the Poisson Surface Reconstruction code. It has evolved to support more general adaptive finite-elements systems:
<UL>
<LI> in spaces of arbitrary dimension,
<LI> discretized using finite-elements of arbitrary degree,
<LI> involving arbitrary function derivatives,
<LI> with both point-wise and integrated constraints.
</UL>
<hr>
<a name="LINKS"><b>LINKS</b></a><br>
<ul>
<b>Papers:</b>
<a href="http://www.cs.jhu.edu/~misha/MyPapers/SGP06.pdf">[Kazhdan, Bolitho, and Hoppe, 2006]</a>,
<a href="http://www.agarwala.org/efficient_gdc/">[Agarwala, 2007]</A>
<a href="http://mesh.brown.edu/ssd/paper.html">[Calakli and Taubin, 2011]</a>,
<A HREF="https://www.cs.cmu.edu/~kmcrane/Projects/HeatMethod/">[Crane, Weischedel, and Wardetzky, 2013]</a>,
<a href="http://www.cs.jhu.edu/~misha/MyPapers/ToG13.pdf">[Kazhdan and Hoppe, 2013]</a>
<br>
<b>Executables: </b>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/AdaptiveSolvers.x64.zip">Win64</a><br>
<b>Source Code:</b>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/AdaptiveSolvers.zip">ZIP</a> <a href="https://github.com/mkazhdan/PoissonRecon">GitHub</a><br>
<b>Older Versions:</b>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version9.011/">V9.011</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version9.01/">V9.01</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version9.0/">V9.0</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version8.0/">V8.0</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version7.0/">V7.0</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.13a/">V6.13a</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.13/">V6.13</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.12/">V6.12</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.11/">V6.11</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.1/">V6.1</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6/">V6</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.71/">V5.71</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.6/">V5.6</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.5a/">V5.5a</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.1/">V5.1</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5/">V5</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version4.51/">V4.51</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version4.5/">V4.5</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version4/">V4</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version3/">V3</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version2/">V2</a>,
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version1/">V1</a>
</ul>
<hr>
<a name="EXECUTABLES"><b>EXECUTABLES</b></a> (<A HREF="#PoissonRecon">PoissonRecon</A>, <A HREF="#SSDRecon">SSDRecon</A>)<br>
<ul>
<dl>
<font size="+1"><b><a name="PoissonRecon">PoissonRecon</a></b></font><BR>
Reconstructs a triangle mesh from a set of oriented 3D points by solving a Poisson system (solving a 3D Laplacian system with positional value constraints) <a href="http://www.cs.jhu.edu/~misha/MyPapers/SGP06.pdf">[Kazhdan, Bolitho, and Hoppe, 2006]</a>,
<a href="http://www.cs.jhu.edu/~misha/MyPapers/ToG13.pdf">[Kazhdan and Hoppe, 2013]</a>
<dt><b>--in</b> &lt;<i>input points</i>&gt;
</dt><dd> This string is the name of the file from which the point set will be read.<br>
If the file extension is <i>.ply</i>, the file should be in
<a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format, giving the list of oriented
vertices with the x-, y-, and z-coordinates of the positions encoded by the properties <i>x</i>, <i>y</i>, and
<i>z</i> and the x-, y-, and z-coordinates of the normals encoded by the properties <i>nx</i>, <i>ny</i>, and
<i>nz</i> .<br>
If the file extension is <i>.bnpts</i>, the file should be a binary file, consisting of blocks of 6 32-bit
floats: x-, y-, and z-coordinates of the point's position, followed by the x-, y-, and z-coordinates
of the point's normal. (No information about the number of oriented point samples should be specified.)<br>
Otherwise, the file should be an ascii file with groups of 6,
white space delimited, numbers: x-, y-, and z-coordinates of the point's position, followed
by the x-, y- and z-coordinates of the point's normal. (No information about the number of oriented point samples should be specified.)<br> 

</dd><dt>[<b>--out</b> &lt;<i>output triangle mesh</i>&gt;]
</dt><dd> This string is the name of the file to which the triangle mesh will be written. 
The file is written in <a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format.

</dd><dt>[<b>--tree</b> &lt;<i>output octree and coefficients</i>&gt;]
</dt><dd> This string is the name of the file to which the the octree and solution coefficients are to be written.

</dd><dt>[<b>--voxel</b> &lt;<i>output voxel grid</i>&gt;]
</dt><dd> This string is the name of the file to which the sampled implicit function will be written.
The file is written out in binary, with the first 4 bytes corresponding to the (integer) sampling resolution, 2^<i>d</i>,
and the next 4 x 2^<i>d</i> x 2^<i>d</i> x 2^<i>d</i> bytes corresponding to the (single precision) floating point values
of the implicit function.

</dd><dt>[<b>--degree</b> &lt;<i>B-spline degree</i>&gt;]
</dt><dd> This integer specifies the degree of the B-spline that is to be used to define the finite elements system.
Larger degrees support higher order approximations, but come at the cost of denser system matrices (incurring a cost in both space and time).<br>
The default value for this parameter is 2.

</dd><dt>[<b>--bType</b> &lt;<i>boundary type</i>&gt;]
</dt><dd> This integer specifies the boundary type for the finite elements. Valid values are:
<ul>
<li> <b>1</b>: Free boundary constraints
</li><li> <b>2</b>: Dirichlet boundary constraints
</li><li> <b>3</b>: Neumann boundary constraints
</li></ul>
The default value for this parameter is 3 (Neumann).

</dd><dt>[<b>--depth</b> &lt;<i>reconstruction depth</i>&gt;]
</dt><dd> This integer is the maximum depth of the tree that will be used for surface reconstruction.
Running at depth <i>d</i> corresponds to solving on a voxel grid whose resolution is no larger than
2^<i>d</i> x 2^<i>d</i> x 2^<i>d</i>. Note that since the reconstructor adapts the octree to the
sampling density, the specified reconstruction depth is only an upper bound.<br>
The default value for this parameter is 8.

</dd><dt>[<b>--width</b> &lt;<i>finest cell width</i>&gt;]
</dt><dd> This floating point value specifies the target width of the finest level octree cells.<br>
This parameter is ignored if the <B>--depth</B> is also specified.

</dd><dt>[<b>--scale</b> &lt;<i>scale factor</i>&gt;]
</dt><dd> This floating point value specifies the ratio between the diameter of the cube used for reconstruction
and the diameter of the samples' bounding cube.<br>
The default value is 1.1.

</dd><dt>[<b>--samplesPerNode</b> &lt;<i>minimum number of samples</i>&gt;]
</dt><dd> This floating point value specifies the minimum number of sample points that should fall within an
octree node as the octree construction is adapted to sampling density. For noise-free samples, small values
in the range [1.0 - 5.0] can be used. For more noisy samples, larger values in the range [15.0 - 20.0] may
be needed to provide a smoother, noise-reduced, reconstruction.<br>
The default value is 1.0.

</dd><dt>[<b>--pointWeight</b> &lt;<i>interpolation weight</i>&gt;]
</dt><dd> This floating point value specifies the importance that interpolation of the point samples
is given in the formulation of the screened Poisson equation.<br>
The results of the original (unscreened) Poisson Reconstruction can be obtained by setting this value to 0.<br>
The default value for this parameter is twice the B-spline degree.

</dd><dt>[<b>--iters</b> &lt;<i>Gauss-Seidel iterations per level</i>&gt;]
</dt><dd> This integer value specifies the number of Gauss-Seidel relaxations to be performed at each level of the octree hierarchy.<br>
The default value for this parameter is 8.

</dd><dt>[<b>--density</b>]
</dt><dd> Enabling this flag tells the reconstructor to output the estimated depth values of the iso-surface vertices.

</dd><dt>[<b>--normals</b>]
</dt><dd> Enabling this flag tells the reconstructor to output vertex normals, computed from the gradients of the implicit function.

</dd><dt>[<b>--colors</b>]
</dt><dd> Enabling this flag tells the reconstructor to read in color values with the input points and extrapolate those to the vertices of the output.

</dd><dt>[<b>--data</b> &lt;<i>pull factor</i>&gt;]
</dt><dd> If <B>--colors</B> is specified, this floating point value specifies the relative importance
of finer color estimates over lower ones.<BR>
The default value for this parameter is 32.

</dd><dt>[<b>--confidence</b> &lt;<i>normal confidence exponent</i>&gt;]
</dt><dd> This floating point value specifies the exponent to be applied to a point's confidence to adjust its weight. (A point's confidence is defined by the magnitude of its normal.)<BR>
The default value for this parameter is 0.

</dd><dt>[<b>--confidenceBias</b> &lt;<i>normal confidence bias exponent</i>&gt;]
</dt><dd> This floating point value specifies the exponent to be applied to a point's confidence to bias the resolution at which the sample contributes to the linear system. (Points with lower confidence are biased to contribute at coarser resolutions.)<BR>
The default value for this parameter is 0.

</dd><dt>[<b>--primalVoxel</b>]
</dt><dd> Enabling this flag when outputing to a voxel file has the reconstructor sample the implicit function at the corners of the grid, rather than the centers of the cells.

</dd><dt>[<b>--linearFit</b>]
</dt><dd> Enabling this flag has the reconstructor use linear interpolation to estimate the positions of iso-vertices.

</dd><dt>[<b>--polygonMesh</b>]
</dt><dd> Enabling this flag tells the reconstructor to output a polygon mesh (rather than triangulating the results of Marching Cubes).

</dd><dt>[<b>--tempDir</b> &lt;<i>temporary output directory</i>&gt;]
</dt><dd> This string is the name of the directory to which temporary files will be written.

</dd><dt>[<b>--threads</b> &lt;<i>number of processing threads</i>&gt;]
</dt><dd> This integer specifies the number of threads across which the algorithm should be parallelized.<br>
The default value for this parameter is equal to the numer of (virtual) processors on the executing  machine.

</dd><dt>[<b>--maxMemory</b> &lt;<i>maximum memory usage (in GB)</i>&gt;]
</dt><dd> If positive, this integer value specifies the peak memory utilization for running the reconstruction code (forcing the execution to terminate if the limit is exceeded).

</dd><dt>[<b>--performance</b>]
</dt><dd> Enabling this flag provides running time and peak memory usage at the end of the execution.

</dd><dt>[<b>--verbose</b>]
</dt><dd> Enabling this flag provides a more verbose description of the running times and memory usages of individual components of the surface reconstructor.

</dd>
</dl>
</ul>


<ul>
<dl>
<font size="+1"><b><a NAME="SSDRecon">SSDRecon</a></b></font><BR>
Reconstructs a surface mesh from a set of oriented 3D points by solving for a Smooth Signed Distance function (solving a 3D bi-Laplacian operator with positional value and gradient constraints) <a href="http://mesh.brown.edu/ssd/paper.html">[Calakli and Taubin, 2011]</a>,

<dt><b>--in</b> &lt;<i>input points</i>&gt;
</dt><dd> This string is the name of the file from which the point set will be read.<br>
If the file extension is <i>.ply</i>, the file should be in
<a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format, giving the list of oriented
vertices with the x-, y-, and z-coordinates of the positions encoded by the properties <i>x</i>, <i>y</i>, and
<i>z</i> and the x-, y-, and z-coordinates of the normals encoded by the properties <i>nx</i>, <i>ny</i>, and
<i>nz</i> .<br>
If the file extension is <i>.bnpts</i>, the file should be a binary file, consisting of blocks of 6 32-bit
floats: x-, y-, and z-coordinates of the point's position, followed by the x-, y-, and z-coordinates
of the point's normal. (No information about the number of oriented point samples should be specified.)<br>
Otherwise, the file should be an ascii file with groups of 6,
white space delimited, numbers: x-, y-, and z-coordinates of the point's position, followed
by the x-, y- and z-coordinates of the point's normal. (No information about the number of oriented point samples should be specified.)<br> 

</dd><dt>[<b>--out</b> &lt;<i>output triangle mesh</i>&gt;]
</dt><dd> This string is the name of the file to which the triangle mesh will be written. 
The file is written in <a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format.

</dd><dt>[<b>--tree</b> &lt;<i>output octree and coefficients</i>&gt;]
</dt><dd> This string is the name of the file to which the the octree and solution coefficients are to be written.

</dd><dt>[<b>--voxel</b> &lt;<i>output voxel grid</i>&gt;]
</dt><dd> This string is the name of the file to which the sampled implicit function will be written.
The file is wrtten out in binary, with the first 4 bytes corresponding to the (integer) sampling resolution, 2^<i>d</i>,
and the next 4 x 2^<i>d</i> x 2^<i>d</i> x 2^<i>d</i> bytes corresponding to the (single precision) floating point values
of the implicit function.

</dd><dt>[<b>--degree</b> &lt;<i>B-spline degree</i>&gt;]
</dt><dd> This integer specifies the degree of the B-spline that is to be used to define the finite elements system.
Larger degrees support higher order approximations, but come at the cost of denser system matrices (incurring a cost in both space and time).<br>
The default value for this parameter is 2.

</dd><dt>[<b>--depth</b> &lt;<i>reconstruction depth</i>&gt;]
</dt><dd> This integer is the maximum depth of the tree that will be used for surface reconstruction.
Running at depth <i>d</i> corresponds to solving on a voxel grid whose resolution is no larger than
2^<i>d</i> x 2^<i>d</i> x 2^<i>d</i>. Note that since the reconstructor adapts the octree to the
sampling density, the specified reconstruction depth is only an upper bound.<br>
The default value for this parameter is 8.

</dd><dt>[<b>--width</b> &lt;<i>finest cell width</i>&gt;]
</dt><dd> This floating point value specifies the target width of the finest level octree cells.<br>
This parameter is ignored if the <B>--depth</B> is also specified.

</dd><dt>[<b>--scale</b> &lt;<i>scale factor</i>&gt;]
</dt><dd> This floating point value specifies the ratio between the diameter of the cube used for reconstruction
and the diameter of the samples' bounding cube.<br>
The default value is 1.1.

</dd><dt>[<b>--samplesPerNode</b> &lt;<i>minimum number of samples</i>&gt;]
</dt><dd> This floating point value specifies the minimum number of sample points that should fall within an
octree node as the octree construction is adapted to sampling density. For noise-free samples, small values
in the range [1.0 - 5.0] can be used. For more noisy samples, larger values in the range [15.0 - 20.0] may
be needed to provide a smoother, noise-reduced, reconstruction.<br>
The default value is 1.0.

</dd><dt>[<b>--valueWeight</b> &lt;<i>zero-crossing interpolation weight</i>&gt;]
</dt><dd> This floating point value specifies the importance that interpolation of the point samples
is given in the formulation of the screened Smoothed Signed Distance Reconstruction.<br>
The default value for this parameter is 1.

</dd><dt>[<b>--gradientWeight</b> &lt;<i>normal interpolation weight</i>&gt;]
</dt><dd> This floating point value specifies the importance that interpolation of the points' normals
is given in the formulation of the screened Smoothed Signed Distance Reconstruction.<br>
The default value for this parameter is 1.

</dd><dt>[<b>--biLapWeight</b> &lt;<i>bi-Laplacian weight weight</i>&gt;]
</dt><dd> This floating point value specifies the importance that the bi-Laplacian regularization
is given in the formulation of the screened Smoothed Signed Distance Reconstruction.<br>
The default value for this parameter is 1.

</dd><dt>[<b>--iters</b> &lt;<i>GS iters</i>&gt;]
</dt><dd> This integer value specifies the number of Gauss-Seidel relaxations to be performed at each level of the hiearchy.<br>
The default value for this parameter is 8.

</dd><dt>[<b>--density</b>]
</dt><dd> Enabling this flag tells the reconstructor to output the estimated depth values of the iso-surface vertices.

</dd><dt>[<b>--normals</b>]
</dt><dd> Enabling this flag tells the reconstructor to output vertex normals, computed from the gradients of the implicit function.

</dd><dt>[<b>--colors</b>]
</dt><dd> Enabling this flag tells the reconstructor to read in color values with the input points and extrapolate those to the vertices of the output.

</dd><dt>[<b>--data</b> &lt;<i>pull factor</i>&gt;]
</dt><dd> If <B>--colors</B> is specified, this floating point value specifies the relative importance
of finer color estimates over lower ones.<BR>
The default value for this parameter is 32.

</dd><dt>[<b>--confidence</b> &lt;<i>normal confidence exponent</i>&gt;]
</dt><dd> This floating point value specifies the exponent to be applied to a point's confidence to adjust its weight. (A point's confidence is defined by the magnitude of its normal.)<BR>
The default value for this parameter is 0.

</dd><dt>[<b>--confidenceBias</b> &lt;<i>normal confidence bias exponent</i>&gt;]
</dt><dd> This floating point value specifies the exponent to be applied to a point's confidence to bias the resolution at which the sample contributes to the linear system. (Points with lower confidence are biased to contribute at coarser resolutions.)<BR>
The default value for this parameter is 0.

</dd><dt>[<b>--primalVoxel</b>]
</dt><dd> Enabling this flag when outputing to a voxel file has the reconstructor sample the implicit function at the corners of the grid, rather than the centers of the cells.

</dd><dt>[<b>--nonLinearFit</b>]
</dt><dd> Enabling this flag has the reconstructor use quadratic interpolation to estimate the positions of iso-vertices.

</dd><dt>[<b>--polygonMesh</b>]
</dt><dd> Enabling this flag tells the reconstructor to output a polygon mesh (rather than triangulating the results of Marching Cubes).

</dd><dt>[<b>--tempDir</b> &lt;<i>temporary output directory</i>&gt;]
</dt><dd> This string is the name of the directory to which temporary files will be written.

</dd><dt>[<b>--threads</b> &lt;<i>number of processing threads</i>&gt;]
</dt><dd> This integer specifies the number of threads across which the algorithm should be parallelized.<br>
The default value for this parameter is equal to the numer of (virtual) processors on the executing  machine.

</dd><dt>[<b>--maxMemory</b> &lt;<i>maximum memory usage (in GB)</i>&gt;]
</dt><dd> If positive, this integer value specifies the peak memory utilization for running the reconstruction code (forcing the execution to terminate if the limit is exceeded).

</dd><dt>[<b>--performance</b>]
</dt><dd> Enabling this flag provides running time and peak memory usage at the end of the execution.

</dd><dt>[<b>--verbose</b>]
</dt><dd> Enabling this flag provides a more verbose description of the running times and memory usages of
individual components of the surface reconstructor.

</dd>
</dl>
</ul>


<ul>
<dl>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" onclick="toggleAll( $(&#39;surface_trimmer&#39;) ) ; return false;">SurfaceTrimmer</a></b></font><BR>
Trims off parts of a triangle mesh with a per-vertex signal whose value falls below a threshold (used for removing parts of a reconstructed surface that are generated in low-sampling-density regions)

<dt><b>--in</b> &lt;<i>input triangle mesh</i>&gt;
</dt><dd> This string is the name of the file from which the triangle mesh will be read. 
The file is read in <a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format and it is assumed that the vertices have a <i>value</i> field which stores the signal's value. (When run with <b>--density</b> flag, the reconstructor will output this field with the mesh vertices.)

</dd><dt><b>--trim</b> &lt;<i>trimming value</i>&gt;
</dt><dd> This floating point values specifies the value for mesh trimming. The subset of the mesh with signal value less than the trim value is discarded.

</dd><dt>[<b>--out</b> &lt;<i>output triangle mesh</i>&gt;]
</dt><dd> This string is the name of the file to which the triangle mesh will be written. 
The file is written in <a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format.

</dd><dt>[<b>--smooth</b> &lt;<i>smoothing iterations</i>&gt;]
</dt><dd> This integer values the number of umbrella smoothing operations to perform on the signal before trimming.<br>
The default value is 5.

</dd><dt>[<b>--aRatio</b> &lt;<i>island area ratio</i>&gt;]
</dt><dd> This floating point value specifies the area ratio that defines a disconnected component as an "island". Connected components whose area, relative to the total area of the mesh, are smaller than this value will be merged into the output surface to close small holes, and will be discarded from the output surface to remove small disconnected components.<br>
The default value 0.001.

</dd><dt>[<b>--polygonMesh</b>]
</dt><dd> Enabling this flag tells the trimmer to output a polygon mesh (rather than triangulating the trimming results).

</dd><dt>[<b>--verbose</b>]
</dt><dd> Enabling this flag provides a more verbose description of the running times and memory usages of individual components of the surface reconstructor.

</dd>
</dl>
</ul>


<ul>
<dl>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" onclick="toggleAll( $(&#39;image_stitching&#39;) ) ; return false;">ImageStitching</a></b></font><BR>
Stitches together a composite of image tiles into a seamless panorama by solving for the correction term (solving a 2D Laplacian system) <a href="http://www.agarwala.org/efficient_gdc/">[Agarwala, 2007]</A>

<dt><b>--in</b> &lt;<i>input composite image</i>&gt; &lt;<i>input label image</i>&gt;
</dt><dd> This pair of strings give the name of the composite image file and the associated label file.<BR>
All pixels in the composite that come from the same source should be assigned the same color in the label file.<BR>
PNG and JPG files are supported (though only PNG should be used for the label file as it is lossless).

</dd><dt>[<b>--out</b> &lt;<i>output image</i>&gt;]
</dt><dd> This string is the name of the file to which the stitched image will be written.<BR>
PNG and JPG files are supported.

</dd><dt>[<b>--degree</b> &lt;<i>B-spline degree</i>&gt;]
</dt><dd> This integer specifies the degree of the B-spline that is to be used to define the finite elements system.
Larger degrees support higher order approximations, but come at the cost of denser system matrices (incurring a cost in both space and time).<br>
The default value for this parameter is 1.

</dd><dt>[<b>--wScl</b> &lt;<i>successive under-relaxation scale</i>&gt;]
</dt><dd> This floating point value specifies the scale for the adapted successive under-relaxation used to remove ringing.<br>
The default value 0.125.

</dd><dt>[<b>--wExp</b> &lt;<i>successive under-relaxation exponent</i>&gt;]
</dt><dd> This floating point value specifies the exponent for the adapted successive under-relaxation used to remove ringing.<br>
The default value 6.

</dd><dt>[<b>--iters</b> &lt;<i>GS iters</i>&gt;]
</dt><dd> This integer value specifies the number of Gauss-Seidel relaxations to be performed at each level of the hiearchy.<br>
The default value for this parameter is 8.

</dd><dt>[<b>--threads</b> &lt;<i>number of processing threads</i>&gt;]
</dt><dd> This integer specifies the number of threads across which the algorithm should be parallelized.<br>
The default value for this parameter is equal to the numer of (virtual) processors on the executing  machine.

</dd><dt>[<b>--maxMemory</b> &lt;<i>maximum memory usage (in GB)</i>&gt;]
</dt><dd> If positive, this integer value specifies the peak memory utilization for running the code (forcing the execution to terminate if the limit is exceeded).

</dd><dt>[<b>--performance</b>]
</dt><dd> Enabling this flag provides running time and peak memory usage at the end of the execution.

</dd><dt>[<b>--verbose</b>]
</dt><dd> Enabling this flag provides a more verbose description of the running times and memory usages of
individual components of the image stitcher.

</dd>
</dl>
</ul>


<ul>
<dl>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" onclick="toggleAll( $(&#39;edt_in_heat&#39;) ) ; return false;">EDTInHeat</a></b></font><BR>
Computes the unsigned Euclidean Distance Transform of a triangle mesh (solving two 3D Laplacian systems) <A HREF="https://www.cs.cmu.edu/~kmcrane/Projects/HeatMethod/">[Crane, Weischedel, and Wardetzky, 2013]</A>
<dt><b>--in</b> &lt;<i>input mesh</i>&gt;
</dt><dd> This string is the name of the file from which the triangle mesh will be read. 
The file is assumed to be in <a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format.

</dd><dt>[<b>--out</b> &lt;<i>output octree and coefficients</i>&gt;]
</dt><dd> This string is the name of the file to which the the octree and solution coefficients are to be written.

</dd><dt>[<b>--degree</b> &lt;<i>B-spline degree</i>&gt;]
</dt><dd> This integer specifies the degree of the B-spline that is to be used to define the finite elements system.
Larger degrees support higher order approximations, but come at the cost of denser system matrices (incurring a cost in both space and time).<br>
The default value for this parameter is 1.

</dd><dt>[<b>--depth</b> &lt;<i>edt depth</i>&gt;]
</dt><dd> This integer is the maximum depth of the tree that will be used for computing the Euclidean Distance Transform.
Running at depth <i>d</i> corresponds to solving on a voxel grid whose resolution is no larger than
2^<i>d</i> x 2^<i>d</i> x 2^<i>d</i>.<br>
The default value for this parameter is 8.

</dd><dt>[<b>--scale</b> &lt;<i>scale factor</i>&gt;]
</dt><dd> This floating point value specifies the ratio between the diameter of the cube used for computing the EDT
and the diameter of the mesh's bounding cube.<br>
The default value is 2.

</dd><dt>[<b>--diffusion</b> &lt;<i>diffusion time</i>&gt;]
</dt><dd> This floating point value specifies the time-scale for the initial heat diffusion.<BR>
The default value is 0.0005.

</dd><dt>[<b>--valueWeight</b> &lt;<i>zero-crossing interpolation weight</i>&gt;]
</dt><dd> This floating point value specifies the importance that the EDT evaluate to zero at points on the input mesh is given.<br>
The default value for this parameter is 0.01.

</dd><dt>[<b>--wScl</b> &lt;<i>successive under-relaxation scale</i>&gt;]
</dt><dd> This floating point value specifies the scale for the adapted successive under-relaxation used to remove ringing.<br>
The default value 0.125.

</dd><dt>[<b>--wExp</b> &lt;<i>successive under-relaxation exponent</i>&gt;]
</dt><dd> This floating point value specifies the exponent for the adapted successive under-relaxation used to remove ringing.<br>
The default value 6.

</dd><dt>[<b>--iters</b> &lt;<i>GS iters</i>&gt;]
</dt><dd> This integer value specifies the number of Gauss-Seidel relaxations to be performed at each level of the hiearchy.<br>
The default value for this parameter is 8.

</dd><dt>[<b>--threads</b> &lt;<i>number of processing threads</i>&gt;]
</dt><dd> This integer specifies the number of threads across which the algorithm should be parallelized.<br>
The default value for this parameter is equal to the numer of (virtual) processors on the executing  machine.

</dd><dt>[<b>--maxMemory</b> &lt;<i>maximum memory usage (in GB)</i>&gt;]
</dt><dd> If positive, this integer value specifies the peak memory utilization for running the code (forcing the execution to terminate if the limit is exceeded).

</dd><dt>[<b>--performance</b>]
</dt><dd> Enabling this flag provides running time and peak memory usage at the end of the execution.

</dd><dt>[<b>--verbose</b>]
</dt><dd> Enabling this flag provides a more verbose description of the running times and memory usages of individual components of the EDT computation.

</dd>
</dl>
</ul>


<ul>
<dl>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" onclick="toggleAll( $(&#39;adaptive_tree_visualization&#39;) ) ; return false;">AdaptiveTreeVisualization</a></b></font><BR>
Extracts iso-surfaces and a sampling on a regular grid from an implicit function represented over an adapted tree
<dt><b>--in</b> &lt;<i>input tree and coefficients</i>&gt;
</dt><dd> This string is the name of the file from which the tree and implicit functions coefficients are to be read. 

</dd><dt>[<b>--grid</b> &lt;<i>output value grid</i>&gt;]
</dt><dd> This string is the name of the file to which the sampling of the implicit along a regular voxel grid will be written.<BR>
The file is written out in binary, with the first 4 bytes corresponding to the (integer) sampling resolution, <i>R</i>,
and the next 4 x <I>R</I>^<i>D</i> bytes corresponding to the (single precision) floating point values of the implicit function. (Here, <i>D</I> is the dimension.)

</dd><dt>[<b>--primalGrid</b>]
</dt><dd> Enabling this flag when outputing a grid file samples the implicit function at the corners of the grid, rather than the centers of the cells.


</dd><dt>[<b>--mesh</b> &lt;<i>output triangle mesh</i>&gt;]
</dt><dd> This string is the name of the file to which the triangle mesh will be written. 
The file is written in <a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format.<BR>
This is only supported for dimension 3.

</dd><dt>[<b>--iso</b> &lt;<i>iso-value for mesh extraction</i>&gt;]
</dt><dd> This floating point value specifies the iso-value at which the implicit surface is to be extracted.<br>
The default value is 0.

</dd><dt>[<b>--nonLinearFit</b>]
</dt><dd> Enabling this flag has the reconstructor use quadratic interpolation to estimate the positions of iso-vertices.

</dd><dt>[<b>--polygonMesh</b>]
</dt><dd> Enabling this flag tells the reconstructor to output a polygon mesh (rather than triangulating the results of Marching Cubes).

</dd><dt>[<b>--flip</b>]
</dt><dd> Enabling this flag flips the orientations of the output triangles.

</dd><dt>[<b>--threads</b> &lt;<i>number of processing threads</i>&gt;]
</dt><dd> This integer specifies the number of threads across which the algorithm should be parallelized.<br>
The default value for this parameter is equal to the numer of (virtual) processors on the executing  machine.

</dd><dt>[<b>--verbose</b>]
</dt><dd> Enabling this flag provides a more verbose description of the running times and memory usages of
individual components of the visualizer.

</dd>
</dl>
</ul>

<hr>
<a name="USAGE"><b>USAGE EXAMPLES (WITH SAMPLE DATA)</b></a><br>

<ul>
<dl>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" onclick="toggleAll( $(&#39;usage_reconstruction&#39;) ) ; return false;">PoissonRecon / SSDRecon / SurfaceTrimmer</a></b></font>

For testing purposes, three point sets are provided:
<ol>

<li> <a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/horse.npts"><b>Horse</b></a>:
A set of 100,000 oriented point samples (represented in ASCII format) was obtained by sampling a virtual horse model with a sampling density proportional to curvature, giving a set of non-uniformly distributed points.<br>
The surface of the model can be reconstructed by calling the either Poisson surface reconstructor:
<blockquote><code>% PoissonRecon --in horse.npts --out horse.ply --depth 10</code></blockquote>
or the SSD surface reconstructor
<blockquote><code>% SSDRecon --in horse.npts --out horse.ply --depth 10</code></blockquote>
</li>

<li> <a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/bunny.points.ply"><b>Bunny</b></a>:
A set of 362,271 oriented point samples (represented in PLY format) was obtained by merging the data from the original Stanford Bunny
<a href="ftp://graphics.stanford.edu/pub/3Dscanrep/bunny.tar.gz">range scans</a>. The orientation of the sample points was estimated
using the connectivity information within individual range scans.<br>
The original (unscreened) Poisson reconstruction can be obtained by setting the point interpolation weight to zero:
<blockquote><code>% PoissonRecon --in bunny.points.ply --out bunny.ply --depth 10 --pointWeight 0</code></blockquote>
By default, the Poisson surface reconstructor uses degree-2 B-splines. A more efficient reconstruction can be obtained using degree-1 B-splines:
<blockquote><code>% PoissonRecon --in bunny.points.ply --out bunny.ply --depth 10 --pointWeight 0 --degree 1</code></blockquote>
(The SSD reconstructor requires B-splines of degree at least 2 since second derivatives are required to formulate the bi-Laplacian energy.)
</li>

<li> <a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/eagle.points.ply"><b>Eagle</b></a>:
A set of 796,825 oriented point samples with color (represented in PLY format) was obtained in the EPFL <a href="http://lgg.epfl.ch/statues.php">Scanning 3D Statues from Photos</a> course.<br>
A reconstruction of the eagle that extrapolates the color values from the input samples can be obtained by calling:
<blockquote><code>% PoissonRecon --in eagle.points.ply --out eagle.screened.color.ply --depth 10 --colors</code></blockquote>
using the <b>--colors</b> flag to indicate that color extrapolation should be used.<BR>
A reconstruction of the eagle that does not close up the holes can be obtained by first calling:
<blockquote><code>% SSDRecon --in eagle.points.ply --out eagle.screened.color.ply --depth 10 --colors --density</code></blockquote>
using the <b>--density</b> flag to indicate that density estimates should be output with the vertices of the mesh, and then calling:
<blockquote><code>% SurfaceTrimmer --in eagle.screened.color.ply --out eagle.screened.color.trimmed.ply --trim 7</code></blockquote>
to remove all subsets of the surface where the sampling density corresponds to a depth smaller than 7.
</li>

</ol>

</dl>
</ul>


<ul>
<dl>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" onclick="toggleAll( $(&#39;usage_image_stitching&#39;) ) ; return false;">ImageStitching</a></b></font>

For testing purposes, two panoramas are provided: <a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Jaffa.zip"><b>Jaffa</b></a> (23794 x 9492 pixels) and <a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/OldRag.zip"><b>OldRag</b></a> (87722 x 12501 pixels).

A seamless panorama can be obtained by running:
<blockquote><code>% ImageSitching --in pixels.png labels.png --out out.png</code></blockquote>

</dl>
</ul>


<ul>
<dl>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" onclick="toggleAll( $(&#39;usage_edt_in_heat&#39;) ) ; return false;">EDTInHeat / AdaptiveTreeVisualization</a></b></font>
<div id="usage_edt_in_heat" style="display: none;">
The Euclidean Distance Tranform of the reconstructed horse can be obtained by running:
<blockquote><code>% EDTInHeat --in horse.ply --out horse.edt --depth 9</code></blockquote>
Then, the visualization code can be used to extract iso-surfaces from the implicit function.<BR>
To obtain a visualization near the input surface, use an iso-value close to zero:
<blockquote><code>% AdaptiveTreeVisualization.exe --in horse.edt --mesh horse_0.01_.ply --iso 0.01 --flip</code></blockquote>
(By default, the surface is aligned so that the outward facing normal aligns with the negative gradient. Hence, specifying the <CODE>--flip</CODE> flag is used to re-orient the surface.)<BR>
To obtain a visualization closer to the boundary of the bounding box, use an iso-value close to zero:
<blockquote><code>% AdaptiveTreeVisualization.exe --in horse.edt --mesh horse_0.25_.ply --iso 0.25 --flip</code></blockquote>
(Since the default <CODE>--scale</CODE> is 2, a value of 0.25 should still give a surface that is contained within the bounding box.)<BR>
To obtain a sampling of the implicit function over a regular grid:
<blockquote><code>% AdaptiveTreeVisualization.exe --in horse.edt --grid horse.grid</code></blockquote>

</dl>
</ul>


<hr>
<font size="+1"><b><a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version10.00/index.html" name="CHANGES" onclick="toggleAll( $(&#39;changes&#39;) ) ; return false;"><B>HISTORY OF CHANGES</B></a></b></font>
<div id="changes" style="display: none;">
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version3/">Version 3</a>:
<ol>
<li> The implementation of the <b>--samplesPerNode</b> parameter has been modified so that a value of "1" more closely corresponds to a distribution with one sample per leaf node.
</li><li> The code has been modified to support compilation under MSVC 2010 and the associated solution and project files are now provided. (Due to a bug in the Visual Studios compiler, this required modifying the implementation of some of the bit-shifting operators.)
</li></ol>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version4/">Version 4</a>:
<ol>
<li> The code supports screened reconstruction, with interpolation weight specified through the <b>--pointWeight</b> parameter.
</li><li> The code has been implemented to support parallel processing, with the number of threads used for parallelization specified by the <b>--threads</b> parameter.
</li><li> The input point set can now also be in <a href="http://www.cc.gatech.edu/projects/large_models/ply.html">PLY</a> format, and the file-type is determined by the extension, so that the <b>--binary</b> flag is now obsolete.
</li><li> At depths coarser than the one specified by the value <b>--minDepth</b> the octree is no longer adaptive but rather complete, simplifying the prolongation operator.
</li></ol>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version4.5/">Version 4.5</a>:
<ol>
<li> The algorithmic complexity of the solver was reduced from log-linear to linear.
</li></ol>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version4.5/">Version 4.51</a>:
<ol>
<li> Smart pointers were added to ensure that memory accesses were in bounds.
</li></ol>
<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5/">Version 5</a>:
<ol>
<li> The <b>--density</b> flag was added to the reconstructor to output the estimated depth of the iso-vertices.
</li><li> The <i>SurfaceTrimmer</i> executable was added to support trimming off the subset of the reconstructed surface that are far away from the input samples, thereby allowing for the generation of non-water-tight surface.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.1/">Version 5.1</a>:
<ol>
<li> Minor bug-fix to address incorrect neighborhood estimation in the octree finalization.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.5a/">Version 5.5a</a>:
<ol>
<li> Modified to support depths greater than 14. (Should work up to 18 or 19 now.)
</li><li> Improved speed and memory performance by removing the construction of integral and value tables.
</li><li> Fixed a bug in Version 5.5 that used memory and took more time without doing anything useful.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.6/">Version 5.6</a>:
<ol>
<li> Added the <b>--normalWeight</b> flag to support setting a point's interpolation weight in proportion to the magnitude of its normal.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.7/">Version 5.7</a>:
<ol>
<li> Modified the setting of the constraints, replacing the map/reduce implementation with OpenMP atomics to reduce memory usage.
</li><li> Fixed bugs that caused numerical overflow when processing large point clouds on multi-core machines.
</li><li> Improved efficiency of the iso-surface extraction phse.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version5.71/">Version 5.71</a>:
<ol>
<li> Added the function <i>GetSolutionValue</i> to support the evaluation of the implicit function at a specific point.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6/">Version 6</a>:
<ol>
<li> Modified the solver to use Gauss-Seidel relaxation instead of conjugate-gradients at finer resolution.
</li><li> Re-ordered the implementation of the solver so that only a windowed subset of the matrix is in memory at any time, thereby reducing the memory usage during the solver phase.
</li><li> Separated the storage of the data associated with the octree nodes from the topology.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.1/">Version 6.1</a>:
<ol>
<li> Re-ordered the implementation of the iso-surface extraction so that only a windowed subset of the octree is in memory at any time, thereby reducing the memory usage during the extracted phase.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.11/">Version 6.11</a>:
<ol>
<li> Fixed a bug that created a crash in the evaluation phase when <b>--pointWeight</b> is set zero.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.12/">Version 6.12</a>:
<ol>
<li> Removed the OpenMP <i>firstprivate</i> directive as it seemed to cause trouble under Linux compilations.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.13/">Version 6.13</a>:
<ol>
<li> Added a <b>MemoryPointStream</b> class in <i>PointStream.inl</i> to support in-memory point clouds.
</li><li> Modified the signature of <u>Octree::SetTree</u> in <i>MultiGridOctreeData.h</i> to take in a pointer to an object of type <b>PointStream</b> rather than a file-name.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version6.13a/">Version 6.13a</a>:
<ol>
<li> Modified the signature of <u>Octree::SetIsoSurface</u> to rerun a <i>void</i>. [<a href="http://www.danielgm.net/cc/">cloudcompare</a>]
</li><li> Added a definition of <u>SetIsoVertexValue</u> supporting double precision vertices. [<a href="http://www.danielgm.net/cc/">cloudcompare</a>]
</li><li> Removed <i>Time.[h/cpp]</i> from the repository. [<a href="http://www.danielgm.net/cc/">cloudcompare</a>/<a href="http://asmaloney.com/">asmaloney</a>]
</li><li> Fixed assignment bug in <u>Octree::SetSliceIsoVertices</u>. [<a href="http://asmaloney.com/">asmaloney</a>]
</li><li> Fixed initialization bug in <u>SortedTreeNodes::SliceTableData</u> and <u>SortedTreeNodes::XSliceTableData</u>. [<a href="http://asmaloney.com/">asmaloney</a>]
</li><li> Included <i>stdlib.h</i> in <i>Geometry.h</i>. [<a href="http://asmaloney.com/">asmaloney</a>]
</li><li> Fixed default value bug in declaration of <u>Octree::SetTree</u>. [<a href="http://asmaloney.com/">asmaloney</a>]
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version7.0/">Version 7.0</a>:
<ol>
<li> Added functionality to support color extrapolation if present in the input.
</li><li> Modified a bug with the way in which sample contributions were scaled.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version8.0/">Version 8.0</a>:
<ol>
<li> Added support for different degree B-splines.
(Note that as the B-spline degree is a template parameter, only degree 1 through 4 are supported.
If higher order degrees are desired, additional template parameters can be easily added in the body of the <u>Execute</u> function inside of <i>PoissonRecon.cpp</i>.
Similarly, to reduce compilation times, support for specific degrees can be removed.)
</li><li> Added the <b>--primalVoxel</b> flag to support to extraction of a voxel grid using primal sampling.
</li><li> Changed the implementation of the voxel sampling so that computation is now linear, rather than log-linear, in the number of samples.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version9.0/">Version 9.0</a>:
<ol>
<li> Added support for free boundary conditions.
</li><li> Extended the solver to support more general linear systems. This makes it possible to use the same framework to implement the <a href="http://mesh.brown.edu/ssd/">Smoothed Signed Distance Reconstruction</a> of Calakli and Taubin (2011).
</li><li> Modified the implementation of density estimation and input representation. This tends to define a slightly larger system. On its own, this results in slightly increased running-time/footprint for full-res reconstructions, but provides a substantially faster implementation when the output complexity is smaller than the input.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version9.01/">Version 9.01</a>:
<ol>
<li> Reverted the density estimation to behave as in Version 8.0.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version9.01/">Version 9.011</a>:
<ol>
<li> Added a parameter for specifying the temporary directory.
</li></ol>

<a href="http://www.cs.jhu.edu/~misha/Code/PoissonRecon/Version9.01/">Version 10.00</a>:
<ol>
<li> The code has been reworked to support arbitrary dimensions, finite elements of arbitrary degree, generally SPD systems in the evaluated/integrated values and derivatives of the functions, etc.</LI>
<LI> For the reconstruction code, added the <B>--width</B> flag which allows the system to compute the depth of the octree given a target depth for the finest resolution nodes.</LI>
<LI> For the reconstruction code, fixed a bug in the handling of the confidence encoded in the lengths of the normals. In addition, added the flags <B>--confidence</B> and <B>--confidenceBias</B> which allow the user more control of how confidence is used to affect the contribution of a sample.</LI>
</ol>


<hr>
<a name="SUPPORT"><b>SUPPORT</b></a><br>
This work genersouly supported by NSF grants #0746039 and #1422325.

<hr>
<a href="http://www.cs.jhu.edu/~misha">HOME</a>
