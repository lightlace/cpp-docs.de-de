---
title: Linkertoolwarnung LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: 344c219fa1f3daa1e5f9c31431e608f5e7036400
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991155"
---
# <a name="linker-tools-warning-lnk4247"></a>Linkertoolwarnung LNK4247

der Einstiegspunkt "decorated_function_name" hat bereits ein Thread Attribut. "Attribut" wird ignoriert.

Ein Einstiegspunkt, der mit [/Entry (Einstiegspunkt Symbol)](../../build/reference/entry-entry-point-symbol.md)angegeben wurde, hatte ein Threading Attribut, aber [/CLRTHREADATTRIBUTE (Set CLR Thread Attribute)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) wurde ebenfalls mit einem anderen Threading Modell angegeben.

Der Linker hat den mit/CLRTHREADATTRIBUTE. angegebenen Wert ignoriert.

So beheben Sie diese Warnung:

- Entfernen Sie/CLRTHREADATTRIBUTE aus dem Build.

- Entfernen Sie das Attribut aus der Quell Code Datei.

- Entfernen Sie sowohl das-Attribut aus der Quelle als auch/CLRTHREADATTRIBUTE aus dem Build, und akzeptieren Sie das CLR-Standard Threading Modell.

- Ändern Sie den Wert, der an/CLRTHREADATTRIBUTE übermittelt wird, damit er dem-Attribut in der Quelle zustimmt.

- Ändern Sie das Attribut in der Quelle, sodass es mit dem an/CLRTHREADATTRIBUTE. über gebenden Wert übereinstimmt.

Im folgenden Beispiel wird Linkertoolwarnung LNK4247 generiert.

```cpp
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```
