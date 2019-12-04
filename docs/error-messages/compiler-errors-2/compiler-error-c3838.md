---
title: Compilerfehler C3838
ms.date: 11/04/2016
f1_keywords:
- C3838
helpviewer_keywords:
- C3838
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
ms.openlocfilehash: 468fc5e8cb6b3a76880f12fe0aab14810f458a90
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741351"
---
# <a name="compiler-error-c3838"></a>Compilerfehler C3838

die explizite Vererbung von "Type" ist nicht möglich.

Der angegebene `type` kann nicht als Basisklasse in einer Klasse fungieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3838 generiert:

```cpp
// C3838a.cpp
// compile with: /clr /c
public ref class B : public System::Enum {};   // C3838
```
