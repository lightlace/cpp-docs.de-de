---
title: Compilerfehler C3488
ms.date: 11/04/2016
f1_keywords:
- C3488
helpviewer_keywords:
- C3488
ms.assetid: 0a6fcd76-dd3b-48d7-abb3-22eccda96034
ms.openlocfilehash: ed3cccb77a40ab646c9a6375cf4c182de62aa478
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025058"
---
# <a name="compiler-error-c3488"></a>Compilerfehler C3488

"Var" ist nicht zulässig, wenn der Standarderfassungsmodus ein Modus nach Verweis ist.

Wenn Sie angeben, dass der Standarderfassungsmodus für einen Lambda-Ausdruck ein Modus nach Verweis ist, können Sie keine Variable nach Verweis an die Erfassungsklausel dieses Ausdrucks übergeben.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Übergeben Sie die Variable nicht explizit an die Erfassungsklausel, oder

- geben Sie "nach Verweis" nicht als Standarderfassungsmodus an, oder

- geben Sie "nach Wert" als Standarderfassungsmodus an, oder

- übergeben Sie die Variable nach Wert an die Erfassungsklausel. (Dies kann das Verhalten des lambda-Ausdrucks ändern.)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3488 generiert, weil ein Verweis auf die Variable `n` in der Erfassungsklausel eines Lambda-Ausdrucks angezeigt wird, dessen Standarderfassungsmodus der Modus nach Verweis ist:

```
// C3488a.cpp

int main()
{
   int n = 5;
   [&, &n]() { return n; } (); // C3488
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden vier mögliche Lösungen für den Fehler C3488 gezeigt:

```
// C3488b.cpp

int main()
{
   int n = 5;

   // Possible resolution 1:
   // Do not explicitly pass &n to the capture clause.
   [&]() { return n; } ();

   // Possible resolution 2:
   // Do not specify by-reference as the default capture mode.
   [&n]() { return n; } ();

   // Possible resolution 3:
   // Specify by-value as the default capture mode.
   [=, &n]() { return n; } ();

   // Possible resolution 4:
   // Pass n by value to the capture clause.
   [n]() { return n; } ();
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)