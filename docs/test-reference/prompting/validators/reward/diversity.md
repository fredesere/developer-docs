---
sidebar_label: diversity
title: prompting.validators.reward.diversity
---

#### mean\_pooling

```python
def mean_pooling(model_output, attention_mask)
```

Applies mean pooling to the token embeddings generated by the model.

**Arguments**:

- `model_output` _torch.Tensor_ - Embedding model output, where the first element contains token embeddings.
- `attention_mask` _torch.Tensor_ - Attention mask to indicate valid tokens.

**Returns**:

- `torch.Tensor` - Mean-pooled representation of the token embeddings.

**Notes**:

  - The function calculates the mean-pooled representation using the attention mask for valid tokens.
  - Input_mask_expanded is created by expanding the attention mask to match the size of token embeddings.
  - The result is obtained by summing the element-wise multiplication of embeddings and input_mask_expanded,
  and dividing it by the sum of input_mask_expanded after clamping its values to a minimum of 1e-9.

## DiversityRewardModel Objects

```python
class DiversityRewardModel(BaseRewardModel)
```

#### get\_embeddings

```python
def get_embeddings(sentences: List[str]) -> "torch.FloatTensor"
```

Runs a forward pass through the model.

**Arguments**:

  sentences (:obj:`List[str]`):
  text message to be encoded.

**Returns**:

  embedding (:obj:`torch.FloatTensor`):
  Embedding for the message.
