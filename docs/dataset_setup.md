# Dataset Setup — Sen1Floods11 (India Subset)

Oracle-D's satellite module trains on the India subset of the [Sen1Floods11](https://github.com/cloudtostreet/Sen1Floods11) dataset — hand-labeled Sentinel-1 SAR imagery with flood masks. This isn't bundled in the repo due to size; follow these steps to set it up locally.

## 1. Download the dataset

Create a free account at [kaggle.com](https://kaggle.com) if you don't have one, then download:

**[SEN1FLOODS11-essentials](https://www.kaggle.com/datasets/smabrarrajin/sen1floods11-essentials)** (hand-labeled subset only)

Extract the downloaded `.zip` to a temporary folder, e.g. `C:\Projects\raw_sen1floods11\`.

## 2. Sort the India files into the expected structure

The training script expects only `India_*.tif` files, arranged like this:
```
dataset/dataset/sen1floods11_india/
  images/       *_S1Hand.tif
  masks/        *_LabelHand.tif
```

Run this script from the project root (adjust `SRC` to wherever you extracted the zip):

```python
import os, shutil, glob

SRC = "C:/Projects/raw_sen1floods11"
DEST_IMAGES = "dataset/dataset/sen1floods11_india/images"
DEST_MASKS = "dataset/dataset/sen1floods11_india/masks"

os.makedirs(DEST_IMAGES, exist_ok=True)
os.makedirs(DEST_MASKS, exist_ok=True)

for f in glob.glob(f"{SRC}/**/India_*S1Hand.tif", recursive=True):
    shutil.copy(f, DEST_IMAGES)
    print("copied image:", os.path.basename(f))

for f in glob.glob(f"{SRC}/**/India_*LabelHand.tif", recursive=True):
    shutil.copy(f, DEST_MASKS)
    print("copied mask:", os.path.basename(f))
```

## 3. Verify

```powershell
dir dataset\dataset\sen1floods11_india\images
dir dataset\dataset\sen1floods11_india\masks
```
You should see a list of `India_*.tif` files in both folders.

## Note

The `dataset/` folder is git-ignored — never commit these files to the repo. Each teammate needs to run this setup locally once.
