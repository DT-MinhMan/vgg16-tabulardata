# vgg16-tabulardata
- Thông tin các file:
+ vgg16: file tuning cho mô hình vgg16 cho dữ liệu dạng bảng (tabular data)
  * tuning với keras tuner, local loss, dữ liệu gốc
  * tuning với keras tuner, local loss, dữ liệu đã được SMOTE
+ vgg16_default: mô hình vgg16 chưa được tuning
+ mlpKeras_default: mô hình mlp keras chưa tuning
  * tuning với keras tuner, local loss, dữ liệu gốc
  * tuning với keras tuner, local loss, dữ liệu đã được SMOTE
+ improve_mlp: tuning cho mô hình mlp
- Mô hình vgg16 tuning các tham số sau:
+ Cấu trúc CNN (số lượng và kích thước các lớp):
  * num_blocks (số khối Conv-MaxPool, từ 2 đến 4)
  * kernel_size (kích thước filter, chọn 2, 3 hoặc 5)
  * initial_filters (số lượng filter ban đầu, từ 16 đến 64, bước 16)

+ Phần Fully-connected:
  * fc_units_1 (số neuron ở dense đầu, từ 128 đến 1 024, bước 128)
  * dropout_rate (tỷ lệ dropout, từ 0.1 đến 0.5, bước 0.1)
  * fc_units_2 (số neuron ở dense thứ hai, từ 64 đến 512, bước 64)

+ Optimizer & learning rate:
  * learning_rate (chọn trong [1e-4, 5e-4, 1e-3, 5e-3])

+ Tham số của Focal Loss:
  * focal_gamma (γ, từ 1.0 đến 3.0, bước 0.5)
  * focal_alpha (α, từ 0.25 đến 0.75, bước 0.25)
 
- Mô hình mlp tuning các tham số sau:
+ Cấu trúc mạng (Network architecture)
  * num_layers: số lượng hidden layers, từ 1 đến 5
  * Với mỗi layer i từ 0 đến num_layers-1:
  
  units_i: số neuron trong layer, từ 32 đến 512 (bước 32)

  activation_i: hàm kích hoạt, chọn một trong { 'relu', 'tanh', 'elu' }
  
  dropout_i: tỷ lệ dropout sau layer, từ 0.0 đến 0.5 (bước 0.1)

+ Optimizer và learning rate
  * optimizer: chọn một trong { 'adam', 'sgd', 'rmsprop' }
  * learning_rate: tốc độ học, từ 1e-4 đến 1e-2 (sampling logarithmic)


+ Tham số của Focal Loss
  * focal_gamma: γ (gamma) trong công thức focal loss, từ 0.0 đến 5.0 (bước 0.5)
  * focal_alpha: α (alpha) trong công thức focal loss, từ 0.0 đến 1.0 (bước 0.1)
