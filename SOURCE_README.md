# Web Drape test piece

This branch contains the reproducible source build for the Dairon Web Drape test piece.

The GitHub Actions workflow:

1. Restores the supplied `texture-sheet-shipping-palette-v3.png` byte-for-byte from its base64 transport file.
2. Verifies SHA-256 `234286c266e5d9bbfe9a31b4b1694788112f3bd5897907f92e115871f3662264` and 1024 × 1024 dimensions.
3. Uses Blender in background mode to construct one static, flat-shaded mesh, assign one atlas material, save `web_drape.blend`, and export `web_drape.glb`.
4. Reopens the `.blend` and validates the editable source.
5. Parses the `.glb` to verify `TEXCOORD_0`, base-colour atlas use, absence of animation/skin/vertex-colour/normal/metallic-roughness/occlusion/emissive texture data, and exact embedded PNG bytes.

## AI disclosure

OpenAI ChatGPT was used for brief interpretation, topology/design planning, and authorship of the deterministic Blender Python construction and validation scripts. Blender generates the mesh by executing those scripts. No image-to-3D or text-to-3D mesh generator, scan, third-party geometry, or AI-generated presentation image is used in the deliverable geometry or UVs. The supplied atlas is copied byte-for-byte and is not generated, repainted, recoloured, or otherwise altered by AI.
