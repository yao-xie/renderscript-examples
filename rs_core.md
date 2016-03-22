# Introduction #

API specification of rs\_core.rsh


# Details #

**Pack/UnPack Color**
| **Function** | **Description** |
|:-------------|:----------------|
| uchar4 rsPackColorTo8888(float r, float g, float b);<br>uchar4 rsPackColorTo8888(float r, float g, float b, float a); <table><thead><th> Pack floating point (0-1) RGB values into a uchar4.</th></thead><tbody>
<tr><td> uchar4 rsPackColorTo8888(float3 color);<br>uchar4 rsPackColorTo8888(float4 color); </td><td> Pack floating point (0-1) RGB values into a uchar4. </td></tr>
<tr><td> float4 rsUnpackColor8888(uchar4 c); </td><td> Unpack a uchar4 color to float4.  The resulting float range will be (0-1). </td></tr></tbody></table>

<br>

<b>Matrix Operation</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> void rsMatrixSet(rs_matrix4x4 <code>*</code>m, uint32_t row, uint32_t col, float v);<br>void rsMatrixSet(rs_matrix3x3 <code>*</code>m, uint32_t row, uint32_t col, float v);<br>void rsMatrixSet(rs_matrix2x2 <code>*</code>m, uint32_t row, uint32_t col, float v); </td><td> Set one element of a matrix. </td></tr>
<tr><td> float rsMatrixGet(const rs_matrix4x4 <code>*</code>m, uint32_t row, uint32_t col);<br>float rsMatrixGet(const rs_matrix3x3 <code>*</code>m, uint32_t row, uint32_t col);<br>float rsMatrixGet(const rs_matrix2x2 <code>*</code>m, uint32_t row, uint32_t col); </td><td> Get one element of a matrix. </td></tr>
<tr><td> void rsMatrixLoadIdentity(rs_matrix4x4 <code>*</code>m);<br>void rsMatrixLoadIdentity(rs_matrix3x3 <code>*</code>m);<br>void rsMatrixLoadIdentity(rs_matrix2x2 <code>*</code>m); </td><td> Set the elements of a matrix to the identity matrix. </td></tr>
<tr><td> void rsMatrixLoad(rs_matrix4x4 <code>*</code>m, const float <code>*</code>v);<br>void rsMatrixLoad(rs_matrix3x3 <code>*</code>m, const float <code>*</code>v);<br>void rsMatrixLoad(rs_matrix2x2 <code>*</code>m, const float <code>*</code>v); </td><td> Set the elements of a matrix from an array of floats. </td></tr>
<tr><td> void rsMatrixLoad(rs_matrix4x4 <code>*</code>m, const rs_matrix4x4 <code>*</code>v);<br>void rsMatrixLoad(rs_matrix4x4 <code>*</code>m, const rs_matrix3x3 <code>*</code>v);<br>void rsMatrixLoad(rs_matrix4x4 <code>*</code>m, const rs_matrix2x2 <code>*</code>v);<br>void rsMatrixLoad(rs_matrix3x3 <code>*</code>m, const rs_matrix3x3 <code>*</code>v);<br>void rsMatrixLoad(rs_matrix2x2 <code>*</code>m, const rs_matrix2x2 <code>*</code>v); </td><td> Set the elements of a matrix from another matrix. </td></tr>
<tr><td> void rsMatrixLoadRotate(rs_matrix4x4 <code>*</code>m, float rot, float x, float y, float z); </td><td> Load a rotation matrix. </td></tr>
<tr><td> void rsMatrixLoadScale(rs_matrix4x4 <code>*</code>m, float x, float y, float z); </td><td> Load a scale matrix. </td></tr>
<tr><td> void rsMatrixLoadTranslate(rs_matrix4x4 <code>*</code>m, float x, float y, float z); </td><td> Load a translate matrix. </td></tr>
<tr><td> void rsMatrixLoadMultiply(rs_matrix4x4 <code>*</code>m, const rs_matrix4x4 <code>*</code>lhs, const rs_matrix4x4 <code>*</code>rhs);<br>void rsMatrixLoadMultiply(rs_matrix3x3 <code>*</code>m, const rs_matrix3x3 <code>*</code>lhs, const rs_matrix3x3 <code>*</code>rhs);<br>void rsMatrixLoadMultiply(rs_matrix2x2 <code>*</code>m, const rs_matrix2x2 <code>*</code>lhs, const rs_matrix2x2 <code>*</code>rhs); </td><td> Load a multiply matrix. </td></tr>
<tr><td> void rsMatrixMultiply(rs_matrix4x4 <code>*</code>m, const rs_matrix4x4 <code>*</code>rhs);<br>void rsMatrixMultiply(rs_matrix3x3 <code>*</code>m, const rs_matrix3x3 <code>*</code>rhs);<br>void rsMatrixMultiply(rs_matrix2x2 <code>*</code>m, const rs_matrix2x2 <code>*</code>rhs);<br>float4 rsMatrixMultiply(rs_matrix4x4 <code>*</code>m, float4 in);<br>float4 rsMatrixMultiply(rs_matrix4x4 <code>*</code>m, float3 in);<br>float4 rsMatrixMultiply(rs_matrix4x4 <code>*</code>m, float2 in);<br>float3 rsMatrixMultiply(rs_matrix3x3 <code>*</code>m, float3 in);<br>float3 rsMatrixMultiply(rs_matrix3x3 <code>*</code>m, float2 in);<br>float2 rsMatrixMultiply(rs_matrix2x2 <code>*</code>m, float2 in); </td><td> Multiply matrix.   </td></tr>
<tr><td> void rsMatrixRotate(rs_matrix4x4 <code>*</code>m, float rot, float x, float y, float z); </td><td> Rotate matrix.     </td></tr>
<tr><td> void rsMatrixScale(rs_matrix4x4 <code>*</code>m, float x, float y, float z); </td><td> Scale matrix.      </td></tr>
<tr><td> void rsMatrixTranslate(rs_matrix4x4 <code>*</code>m, float x, float y, float z); </td><td> Translate matrix.  </td></tr>
<tr><td> void rsMatrixLoadOrtho(rs_matrix4x4 <code>*</code>m, float left, float right, float bottom, float top, float near, float far); </td><td> Load a ortho matrix. </td></tr>
<tr><td> void rsMatrixLoadFrustum(rs_matrix4x4 <code>*</code>m, float left, float right, float bottom, float top, float near, float far); </td><td> Load a frustum matrix. </td></tr>
<tr><td> void rsMatrixLoadPerspective(rs_matrix4x4 <code>*</code>m, float fovy, float aspect, float near, float far); </td><td> Load a perspective matrix. </td></tr>
<tr><td> bool rsMatrixInverse(rs_matrix4x4 <code>*</code>m);<br>bool rsMatrixInverseTranspose(rs_matrix4x4 <code>*</code>m); </td><td> Returns true if the matrix was successfully inversed. </td></tr>
<tr><td> void rsMatrixTranspose(rs_matrix4x4 <code>*</code>m);<br>void rsMatrixTranspose(rs_matrix3x3 <code>*</code>m);<br>void rsMatrixTranspose(rs_matrix2x2 <code>*</code>m); </td><td> Transpose matrix.  </td></tr></tbody></table>

<b>Integer operation</b>
<table><thead><th> <b>Function</b> </th><th> <b>Description</b> </th></thead><tbody>
<tr><td> uint rsClamp(uint amount, uint low, uint high);<br>int rsClamp(int amount, int low, int high);<br>ushort rsClamp(ushort amount, ushort low, ushort high);<br>short rsClamp(short amount, short low, short high);<br>uchar rsClamp(uchar amount, uchar low, uchar high);<br>char rsClamp(char amount, char low, char high); </td><td>                    </td></tr>