# AK-lab1

## Лістинг:

### calcalator.cpp

```cpp
#include "calculator.h"

double Calculator::Add (double a, double b)
{
	return a + b + 0.5;
}

double Calculator::Sub (double a, double b)
{
    return Add (a, -b);
}

double Calculator::Mul (double a, double b)
{
    return a * b + 0.5;
}

// dividing added
double Calculator::Div (double a, double b)
{
    return a / b + 0.5;
}
```
### calculator.h

```cpp
#ifndef CALCULATOR_H
#define CALCULATOR_H

class Calculator
{
    public:
        double Add (double, double);
        double Sub (double, double);
        double Mul (double, double);
        double Div (double, double); // dividing added
};

#endif//CALCULATOR_H
```
## Патчі: 

### 0001-fix-truncation-error-change-position.patch

```
From d8833ff71cde6c1a336e831d7a28906b26599a41 Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:28:04 +0200
Subject: [PATCH] fix truncation error(swapped committees)

To convert float to integer the truncation is performed, but the
rounding is expected.

Test: Add (4.9, 4.9) should return 10.
Signed-off-by: Sergii Piatakov <sergii.piatakov@globallogic.com>
---
 calculator.cpp | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/calculator.cpp b/calculator.cpp
index b91afea..d93e35b 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -2,7 +2,7 @@
 
 int Calculator::Add (double a, double b)
 {
-    return a + b;
+	return a + b + 0.5;
 }
 
 int Calculator::Sub (double a, double b)
-- 
2.24.0.windows.2
```
### 0001-formatting-use-tabs-instead-of-spaces-changed-positi.patch

```
From 56e02c87201c37ff489ac194e08e8ebe3b5cc3c3 Mon Sep 17 00:00:00 2001
From: Sergii Piatakov <sergii.piatakov@globallogic.com>
Date: Thu, 15 Nov 2018 15:26:35 +0200
Subject: [PATCH] formatting: use tabs instead of spaces(swapped committees)

Signed-off-by: Sergii Piatakov <sergii.piatakov@globallogic.com>
---
 calculator.cpp | 2 +-
 calculator.h   | 6 +++---
 2 files changed, 4 insertions(+), 4 deletions(-)

diff --git a/calculator.cpp b/calculator.cpp
index d93e35b..d10f529 100644
--- a/calculator.cpp
+++ b/calculator.cpp
@@ -7,5 +7,5 @@ int Calculator::Add (double a, double b)
 
 int Calculator::Sub (double a, double b)
 {
-    return Add (a, -b);
+	return Add (a, -b);
 }
diff --git a/calculator.h b/calculator.h
index 3740907..d59d596 100644
--- a/calculator.h
+++ b/calculator.h
@@ -3,9 +3,9 @@
 
 class Calculator
 {
-    public:
-        int Add (double, double);
-        int Sub (double, double);
+	public:
+		int Add (double, double);
+		int Sub (double, double);
 };
 
 #endif//CALCULATOR_H
-- 
2.24.0.windows.2
```

## Висновок

В данній лабораторній роботі були опрацьовані базові команди системи контролю версій **Git**. 
