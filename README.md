# Image-_Genaration_Torch
Image Genaration

import torch
import os
import random
import matplotlib.pyplot as plt

from torch.utils.data import Dataset
from PIL import Image

class dataset(Dataset):
    def __init__(self,data):
        self.data=data
        self.image=os.listdir(data)
    def __len__(self):
        return len(self.image)
    def __getitem__(self,index):
        data_path=os.path.join(
        self.data,self.image[index])
        image=Image.open(data_path)
        return image

data_path='C:\\Users\\yerra\\OneDrive\\Documents\\kaggele datsets\\Grapevine_Leaves_Image_Dataset\\Ak'

Data=dataset(data_path)
print(len(Data))

#Visulazation
plt.imshow(Data[5])
plt.show()
