---
title: Compilerfehler C2870 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47101cbc2fb1be48ba54166b9c6ef99fc0c6c35e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073875"
---
# <a name="compiler-error-c2870"></a>Compilerfehler C2870

'Name': eine Namespace-Definition muss entweder im Dateigültigkeitsbereich oder unmittelbar in einem anderen Namespace-Definition angezeigt werden

Sie definiert Namespace `name` falsch. Namespaces muss definiert werden, im Dateigültigkeitsbereich (außerhalb aller Blöcke und Klassen) oder direkt in einen anderen Namespace.

Im folgende Beispiel wird die C2870 generiert:

```
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```