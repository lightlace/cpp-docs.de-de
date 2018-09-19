---
title: Linkertoolwarnung LNK4247 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d84a5964cb8df5d2973b6031da55d48dade584e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078009"
---
# <a name="linker-tools-warning-lnk4247"></a>Linkertoolwarnung LNK4247

Einstiegspunkt 'Decorated_function_name"verfügt bereits über eine Thread-Attribut; 'Attribut' wird ignoriert

Einen Einstiegspunkt, der mit angegebenen [/Entry (Symbol für Einstiegspunkt)](../../build/reference/entry-entry-point-symbol.md), wies ein, aber [/CLRTHREADATTRIBUTE (festlegen CLR-Threadattributs)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) wurde auch angegeben, mit einem anderen threading-Modell.

Der Linker ignoriert mit/CLRTHREADATTRIBUTE angegebenen Wert.

Um diese Warnung zu beheben:

- Entfernen Sie aus dem Build/CLRTHREADATTRIBUTE.

- Entfernen Sie Attribut aus der Quellcodedatei.

- Entfernen Sie das Attribut aus Quelle "und" / CLRTHREADATTRIBUTE aus dem Build, und akzeptieren Sie die Standard-CLR-Threadingmodell.

- Ändern Sie den Wert, der an die/CLRTHREADATTRIBUTE, übergeben, so, dass es mit dem Attribut in der Quelle zustimmt.

- Ändern Sie das Attribut in der Quelle, so, dass es mit dem Wert, die an/CLRTHREADATTRIBUTE zustimmt.

Im folgende Beispiel wird LNK4247 erzeugt

```
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```