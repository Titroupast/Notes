# 🧠 Weight Decay（权重衰减）笔记

---

## 🔹 1. 是什么

> **Weight Decay = L2 正则化**

👉 在原来的损失函数上，加一个“限制权重大小”的惩罚项：

$$
\text{Loss}_{new} = \text{Loss} + \lambda |w|^2
$$


---

## 🔹 2. 作用（核心）

> ✅ 防止过拟合（最重要）

具体表现：

* 让模型参数不要太大
* 降低模型复杂度
* 提高泛化能力（测试集更好）

---

## 🔹 3. 为什么有效（直觉）

👉 如果权重很大：

* 模型会变得很“激进”
* 更容易记住训练数据（过拟合）

👉 加了 weight decay：

* 有个“力量”一直把权重往 0 拉
* 模型更平滑、更简单

---

## 🔹 4. 对参数更新的影响

原始 SGD：

$$
w = w - lr \cdot \frac{\partial L}{\partial w}
$$
加入 weight decay 后：

$$
w = (1 - lr \cdot \lambda) w - lr \cdot \frac{\partial L}{\partial w}
$$
👉 多了一步：

> **每次更新都会缩小权重（衰减）**

---

## 🔹 5. 在 PyTorch 中的用法

```python
optimizer = torch.optim.SGD(
    params, lr=lr, weight_decay=1e-4
)
```

👉 作用：

> 自动在 loss 中加入 L2 正则项

---

## 🔹 6. 和 SGD / Loss 的关系

训练目标从：

$$
\text{CrossEntropyLoss}
$$
变成：

$$
\text{CrossEntropyLoss} + \lambda |w|^2
$$
👉 SGD 仍然是更新方法，但：

> **优化的目标变了**

---

## 🔹 7. 一句话总结（必背）

> **Weight Decay = 在损失函数中惩罚大权重，让模型更简单，从而减少过拟合**

---

## 🔥 8. 记忆口诀（帮你快速记）

```text
权重大 → 要惩罚  
往 0 拉 → 更稳定  
防过拟合 → 泛化好
```

---

