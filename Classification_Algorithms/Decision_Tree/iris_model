library(rpart)
library(datasets)

sampling_rate = 0.7

data(iris)
iris_train_rows <- sample(1:nrow(iris), sampling_rate * nrow(iris), replace = FALSE)

iris_train <- iris[iris_train_rows,]

iris_fit <- rpart(Species ~ ., data = iris_train)

iris_test <- iris[-iris_train_rows,]

iris_pred <- predict(iris_fit, newdata = iris_test, type = "class")

iris_true_pred <- iris_test[,5]
pred_table <- table(iris_pred,iris_true_pred) 

sum((iris_true_pred == iris_pred))/length(iris_true_pred)

print(iris_fit)