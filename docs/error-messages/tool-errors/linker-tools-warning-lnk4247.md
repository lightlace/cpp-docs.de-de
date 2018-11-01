---
title: Linkertoolwarnung LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: cd4108f8bd06ec7a0b2d2eb9fab13917174b797b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516024"
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