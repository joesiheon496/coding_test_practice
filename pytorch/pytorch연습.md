## 파이토치(PyTorch)개요
- PyTorch는 기계 학습 프레임워크(framework) 중 하나다
  - PyTorch의 텐서(tensor)는 NumPy 배열과 매우 유사
- PyTorch를 사용하면, GPU 연동을 통해 효율적으로 딥러닝 모델을 학습할 수 있다.
```python
import torch
```
## GPU 사용 여부 체크
- 텐서간의 연산을 수행할 때, 기본적으로 두 텐서가 같은 장치에 있어야 한다.
- 가능하면, 연산을 수행하는 텐서들을 모두 GPU에 올린 뒤에 연산을 수행한다.
```python
data = [[1,2],[3,4]]

x = torch.tensor(data)
print(x.is_cuda) # False

x = x.cuda() # GPU로 옮기기
print(x.is_cuda) # True

x = x.cpu() # CPU로 옮기기
print(x.is_cuda) # False
```

- 서로 다른 장치(device)에 있는 텐서끼리 연산을 수행하면 오류가 발생
```python
a = torch.tensor([[1,1],[
```
