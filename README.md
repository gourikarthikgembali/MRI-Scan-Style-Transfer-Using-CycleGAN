# MRI Style Transfer using CycleGAN (T1 ↔ T2)

This project helps to translate **MRI T1 images to T2** and **T2 to T1** using a CycleGAN, trained on MRI scan data. The project demonstrates both directions with example outputs. 

---

## Objective
Use unpaired image-to-image translation (CycleGAN) to generate the **missing MRI modality** (e.g., synthesize T2 from available T1 or vice‑versa), enabling faster workflows and reducing re‑scans in clinical pipelines.

---

## What’s in the project
- **Tasks**: T1 → T2 and T2 → T1 style transfer using CycleGAN. 
- **Data**: MRI scan dataset (unpaired/paired slices). 
- **Notebook outputs**: Visual examples of both conversions. 

---

## Model & Training
- **CycleGAN** with two generators (G\_{T1→T2}, G\_{T2→T1}) and two discriminators (D\_{T2}, D\_{T1}).
- **Losses**: Adversarial, **cycle‑consistency** (enforces T1→T2→T1 and T2→T1→T2), and optional **identity** loss to stabilize mapping.
- **Preprocessing**: resize/crop, intensity normalization; optional augmentation.
- **Metrics**: Visual inspection plus PSNR/SSIM (optional) to compare synthetic vs. target modality.

---

## Quick start
1. **Prepare data**: Organize T1 and T2 slices into separate folders (unpaired is fine). 
2. **Preprocess**: Resize/normalize; build PyTorch/TensorFlow datasets.
3. **Train**: Configure CycleGAN hyperparameters (epochs, lr, λ\_cycle/identity) and start training.
4. **Validate**: Track sample translations each epoch; inspect artifacts.
5. **Evaluate**: (Optional) compute PSNR/SSIM on held‑out pairs.
6. **Infer**: Run G\_{T1→T2} or G\_{T2→T1} to generate missing modality for new studies. 

---

## Business use case
- Fill in **missing MRI sequences** when acquisition time, patient condition, or scanner constraints prevent full protocol.
- Support downstream **diagnostic and planning workflows** where both T1 and T2 views are helpful.
- Reduce **costs and re‑scans** by synthesizing complementary contrasts from available data.

---

## Files
- `MRI_Scan_Style_Transfer_Using_CycleGAN_Project.ipynb` (Jupyter‑converted script) showcasing T1↔T2 conversions and sample images. 
- MRI Scan images data for T1 and T2 modalities
- Generated output image and gif files

---

## Notes
- Validate synthetic images clinically before deployment; use as **decision support**, not a replacement for acquisition.
- Consider domain adaptation (per‑scanner/per‑protocol) and data privacy.

Maintainer: Gouri Karthik Gembali
