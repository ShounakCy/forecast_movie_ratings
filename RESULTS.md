Just Tabular Data
# Model Training and Evaluation Results

## Random Forest Model (Initial Data)

### Best Parameters
- `max_depth`: 15  
- `min_samples_leaf`: 2  
- `min_samples_split`: 5  
- `n_estimators`: 200  

### Performance Metrics
- **MSE:** 0.0869  
- **RMSE:** 0.2948  
- **MAE:** 0.2155  
- **R²:** 0.5727  

---

## CatBoost Model (Initial Data)

### Best Parameters
- `border_count`: 128  
- `depth`: 6  
- `iterations`: 200  
- `l2_leaf_reg`: 5  
- `learning_rate`: 0.1  

### Performance Metrics
- **MSE:** 0.0832  
- **RMSE:** 0.2885  
- **MAE:** 0.2106  
- **R²:** 0.5908  

---

## Models Comparison (Initial Data)
| Model                        | MSE      | RMSE     | MAE      | R²      | Training Time (s) |
|------------------------------|----------|----------|----------|---------|-------------------|
| Random Forest (PCA Features) | 0.086919 | 0.294820 | 0.215536 | 0.572739 | 42.703310         |
| CatBoost (PCA Features)      | 0.083243 | 0.288519 | 0.210589 | 0.590806 | 5.394182          |

---

## Random Forest Model (Combined Data)

### Best Parameters
- `max_depth`: 20  
- `min_samples_leaf`: 2  
- `min_samples_split`: 5  
- `n_estimators`: 200  

### Performance Metrics
- **MSE:** 0.0799  
- **RMSE:** 0.2826  
- **MAE:** 0.2071  
- **R²:** 0.6074  

---

## CatBoost Model (Combined Data)


### Best Parameters
- `border_count`: 128  
- `depth`: 8  
- `iterations`: 200  
- `l2_leaf_reg`: 3  
- `learning_rate`: 0.1  

### Performance Metrics
- **MSE:** 0.0742  
- **RMSE:** 0.2723  
- **MAE:** 0.2003  
- **R²:** 0.6355  

---

## Models Comparison (Combined Data)
| Model                        | MSE      | RMSE     | MAE      | R²      | Training Time (s) |
|------------------------------|----------|----------|----------|---------|-------------------|
| Random Forest (PCA Features) | 0.079875 | 0.282621 | 0.207066 | 0.607366 | 261.677457        |
| CatBoost (PCA Features)      | 0.074157 | 0.272318 | 0.200302 | 0.635472 | 15.100364         |
