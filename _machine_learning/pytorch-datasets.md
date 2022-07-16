---
layout: default
title: PyTorch Dataset's and DataLoader's
---

# PyTorch `Dataset` and `DataLoader`

Two important classes which you can inherit from to build custom dataset classes using your own data. 
 
## `Dataset`

The following is a usable code snippet where each $$(x,y)$$ sample, label pair is defined as a tuple. Each tuple is then stored as an element in a list. We instantiate the following dataset class by passing in this list of tuples. 

```python
from torch.utils.data import Dataset, TensorDataset

class GetDataset(Dataset):
    def __init__(self, data_set): # samples and labels are stored in tuples in data_set (list)
        self.data_distribution = data_set
    
    def __getitem__(self, index):
        sample = self.data_distribution[index][0]
        label = self.data_distribution[index][1]
        return (torch.tensor(sample, dtype=torch.float), torch.tensor(label, dtype=torch.float)) 
    
    def __len__(self):
        return len(self.data_distribution)
```

Instantiate: 

```python
torch_set = GetDataset(data_set)
```

### Split data into train and test sets 

```python
TRAIN_RATIO = 0.8  # 80/20 split (customize to your liking) 
train_size = int(TRAIN_RATIO * len(torch_set))  
test_size = len(torch_set) - train_size
train_dataset, test_dataset = torch.utils.data.random_split(torch_set, [train_size, test_size])
```

## `DataLoader`

These allow us to iterate over batches of the data. 

```python
trainloader = torch.utils.data.DataLoader(train_dataset, batch_size=32)  # change batch size to your liking 
testloader = torch.utils.data.DataLoader(test_dataset, batch_size=1)
```

Example: 

```python
for mini_batch in trainloader:
    sample_points = mini_batch[0]
    sample_labels = mini_batch[1]
    sample_preds = net(sample_points)
    print("The predictions are: ", sample_preds)
    print("Ground truths (label): ", sample_labels) 
```

Why use `DataLoader`'s? It fetches a new data sample when iterating over it. This can have an advantage over just using a `DataSet` when you need to load in the data from a remote server such as Amazon s3. For example, in the data loader, you can specify the path to the current sample in an s3 bucket and have the class code structured such that it fetches the data point and returns it. 





