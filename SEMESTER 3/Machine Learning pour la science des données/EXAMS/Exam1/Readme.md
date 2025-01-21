
### **Solution : Régression Linéaire Simple (SLR)**

#### **1. Détermination du modèle SLR**
Le modèle de régression linéaire simple est défini comme :
\[
y = \theta_0 + \theta_1 x + \epsilon
\]
où :
- \( y \) est la variable dépendante,
- \( x \) est la variable indépendante,
- \( \theta_0 \) (intercept) et \( \theta_1 \) (pente) sont les paramètres du modèle,
- \( \epsilon \) est l'erreur résiduelle.

#### **2. Fonction de perte \( J \)**
La fonction de coût (fonction de perte) utilisée pour la régression linéaire est l'erreur quadratique moyenne (MSE) :
\[
J(\theta_0, \theta_1) = \frac{1}{2n} \sum_{i=1}^{n} (y_i - (\theta_0 + \theta_1 x_i))^2
\]
où \( n \) est le nombre d'échantillons.

#### **3. Calcul du Gradient \( \nabla J \)**
Le gradient de \( J \) est calculé par dérivation partielle :

\[
\frac{\partial J}{\partial \theta_0} = -\frac{1}{n} \sum_{i=1}^{n} (y_i - (\theta_0 + \theta_1 x_i))
\]

\[
\frac{\partial J}{\partial \theta_1} = -\frac{1}{n} \sum_{i=1}^{n} (y_i - (\theta_0 + \theta_1 x_i)) x_i
\]

#### **4. Calcul des paramètres optimaux**
Les valeurs optimales de \( \theta_0 \) et \( \theta_1 \) peuvent être obtenues par la méthode des moindres carrés :

\[
\theta_1 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})}{\sum_{i=1}^{n} (x_i - \bar{x})^2}
\]

\[
\theta_0 = \bar{y} - \theta_1 \bar{x}
\]

où \( \bar{x} \) et \( \bar{y} \) sont les moyennes de \( x \) et \( y \).

---

### **Code Python pour implémenter la régression linéaire**
Voici une implémentation en Python :

```python
import numpy as np

# Données fictives
x = np.array([1, 2, 3, 4, 5])
y = np.array([2, 3, 5, 6, 8])

# Calcul des paramètres optimaux
n = len(x)
x_mean = np.mean(x)
y_mean = np.mean(y)

theta1 = np.sum((x - x_mean) * (y - y_mean)) / np.sum((x - x_mean) ** 2)
theta0 = y_mean - theta1 * x_mean

print(f"Paramètres optimaux: θ0 = {theta0}, θ1 = {theta1}")
```
