# Introduction #

API specification of rs\_graphics.rsh


# Details #

**Binding Program**
| **Function** | **Description** |
|:-------------|:----------------|
| rsgBindProgramFragment(rs\_program\_fragment pf); | Bind the program fragment. |
| rsgBindProgramStore(rs\_program\_store ps); | Bind the program store. |
| rsgBindProgramVertex(rs\_program\_vertex pv); | Bind the program vertex. |
| rsgBindProgramRaster(rs\_program\_raster pr); | Bind the program raster. |
| rsgBindSampler(rs\_program\_fragment, uint slot, rs\_sampler); | Bind the program sampler. |
| rsgBindTexture(rs\_program\_fragment, uint slot, rs\_allocation); | Bind the texture data. |

<br>

<b>Load Matrix</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> rsgProgramVertexLoadProjectionMatrix(const rs_matrix4x4 <b>);</b></td><td> Load vertex matrix as projection matrix. </td></tr>
<tr><td> rsgProgramVertexLoadModelMatrix(const rs_matrix4x4 <b>);</b></td><td> Load vertex matrix as model matrix. </td></tr>
<tr><td> rsgProgramVertexLoadTextureMatrix(const rs_matrix4x4 <b>);</b></td><td> Load vertex matrix as texure matrix. </td></tr>
<tr><td> rsgProgramVertexGetProjectionMatrix(rs_matrix4x4 <b>);</b></td><td> Get the Projection vertex matrix. </td></tr></tbody></table>

<br>

<b>Set constant color</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> rsgProgramFragmentConstantColor(rs_program_fragment pf, float r, float g, float b, float a); </td><td> Set the constant color for a fixed function emulation program. </td></tr></tbody></table>

<br>

<b>Get surface size</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> rsgGetWidth(void); </td><td> Get the width of the current rendering surface. </td></tr>
<tr><td> rsgGetHeight(void); </td><td> Get the height of the current rendering surface. </td></tr></tbody></table>

<br>

<b>Sync memory buffer</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> rsgAllocationSyncAll(rs_allocation alloc); </td><td> Sync the contents of an allocation from its SCRIPT memory space to its HW memory spaces. </td></tr></tbody></table>

<br>

<b>Drawing/Graphics</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> rsgDrawRect(float x1, float y1, float x2, float y2, float z); </td><td> Low performance utility function for drawing a simple rectangle.<br>Not intended for drawing large quantities of geometry. </td></tr>
<tr><td> rsgDrawQuad(float x1, float y1, float z1,<br><code>    </code>float x2, float y2, float z2,<br>float x3, float y3, float z3,<br>float x4, float y4, float z4); </td><td> Low performance utility function for drawing a simple quad.<br>Not intended for drawing large quantities of geometry.</td></tr>
<tr><td> rsgDrawSpriteScreenspace(float x, float y, float z, float w, float h); </td><td> Low performance function for drawing rectangles in screenspace.<br>This function uses the default passthough ProgramVertex.<br>Any bound ProgramVertex is ignored.<br>This function has considerable overhead and should not be used for drawing in shipping applications.</td></tr>
<tr><td> rsgDrawMesh(rs_mesh ism);<br>rsgDrawMesh(rs_mesh ism, uint primitiveIndex);<br>rsgDrawMesh(rs_mesh ism, uint primitiveIndex, uint start, uint len); </td><td> Draw a mesh of geometry using the current context state.<br>The whole mesh is rendered. </td></tr>
<tr><td> rsgClearColor(float r, float g, float b, float a); </td><td> Clears the rendering surface to the specified color.</td></tr>
<tr><td> rsgClearDepth(float value); </td><td> Clears the depth suface to the specified value. </td></tr></tbody></table>

<br>

<b>Drawing/Text</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> rsgDrawText(const char <code>*</code>, int x, int y);<br>rsgDrawText(rs_allocation, int x, int y); </td><td> Draw text string.  </td></tr>
<tr><td> rsgBindFont(rs_font); </td><td> Set the text font. </td></tr>
<tr><td> rsgFontColor(float r, float g, float b, float a); </td><td> Set the text color. </td></tr>
<tr><td> rsgMeasureText(const char <code>*</code>, int <code>*</code>left, int <code>*</code>right, int <code>*</code>top, int <code>*</code>bottom);<br>rsgMeasureText(rs_allocation, int <code>*</code>left, int <code>*</code>right, int <code>*</code>top, int <code>*</code>bottom); </td><td> Returns the bounding box of the text relative to (0, 0).<br>Any of left, right, top, bottom could be NULL </td></tr></tbody></table>

<br>

<b>Misc</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> rsgMeshComputeBoundingBox(rs_mesh mesh, float <code>*</code>minX, float <code>*</code>minY, float <code>*</code>minZ,<br>float <code>*</code>maxX, float <code>*</code>maxY, float <code>*</code>maxZ);<br>rsgMeshComputeBoundingBox(rs_mesh mesh, float3 <code>*</code>bBoxMin, float3 <code>*</code>bBoxMax) {<br>float x1, y1, z1, x2, y2, z2;<br>rsgMeshComputeBoundingBox(mesh, &x1, &y1, &z1, &x2, &y2, &z2);<br>bBoxMin->x = x1;<br>bBoxMin->y = y1;<br>bBoxMin->z = z1;<br>bBoxMax->x = x2;<br>bBoxMax->y = y2;<br>bBoxMax->z = z2;<br>} </td><td>                    </td></tr>