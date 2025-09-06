# Multilayer Perceptron (MLP) & Graph Data Structure

![C++](https://img.shields.io/badge/language-C++-blue.svg)
![Algorithm](https://img.shields.io/badge/algorithm-Graph%20%26%20Backpropagation-green.svg)
![Status](https://img.shields.io/badge/status-academic--project-success.svg)

## 📌 Giới thiệu
Đây là **Bài tập lớn số 3** của môn **Cấu trúc dữ liệu và Giải thuật (CO2003)** – Trường Đại học Bách khoa, ĐHQG TP.HCM.  

Dự án tập trung vào việc xây dựng:
1. **Cấu trúc dữ liệu đồ thị (Graph Data Structure)** với mô hình **đồ thị có hướng** và **đồ thị vô hướng**.  
2. Ứng dụng đồ thị trong việc tính toán **Backpropagation** của **Mạng nơ-ron nhiều lớp (Multilayer Perceptron - MLP)** thông qua **Topological Sorting (Topo Sort)**.

---

## 🚀 Nội dung chính
### 🔹 Task 1: Cấu trúc dữ liệu đồ thị
- Hiện thực các lớp chính:
  - `IGraph<T>`: định nghĩa API chung cho đồ thị.  
  - `AbstractGraph<T>`: lớp trừu tượng với danh sách kề (adjacency list).  
  - `DGraphModel<T>`: hiện thực đồ thị **có hướng**.  
  - `UGraphModel<T>`: hiện thực đồ thị **vô hướng**.  

Các chức năng hỗ trợ:
- Thêm, xóa đỉnh/cạnh.  
- Lấy bậc vào/bậc ra.  
- Kiểm tra liên kết.  
- Duyệt đỉnh, in đồ thị.  

### 🔹 Task 2: Multilayer Perceptron & Backpropagation
- **Forward Pass**: tính đầu ra dựa trên trọng số.  
- **Backward Pass**: lan truyền gradient và cập nhật trọng số.  
- Sử dụng **Topological Sorting (Topo Sort)** để xác định thứ tự tính toán trong DAG.  

Hiện thực:
- `TopoSorter<T>`: hỗ trợ **DFS** và **BFS** topo sort.  
- Hỗ trợ **Stack**, **Queue**, **DLinkedListSE** cho xử lý dữ liệu.  

---

## 📂 Cấu trúc dự án
├── include/
│ └── graph/
│ ├── AbstractGraph.h
│ ├── DGraphModel.h
│ ├── UGraphModel.h
│ └── ...
├── src/
│ ├── main.cpp
│ └── ...
└── README.md

---

## ⚡ Cách biên dịch & chạy
1. Biên dịch dự án:
   ```bash
   g++ src/main.cpp -Iinclude -o mlp
2. Chạy chương trình
   ```bash
   mlp
