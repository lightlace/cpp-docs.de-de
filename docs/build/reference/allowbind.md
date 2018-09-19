---
title: -ALLOWBIND | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ce0a33ebb0b8b9ba34ac241c8335e9524dec08b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715572"
---
# <a name="allowbind"></a>/ALLOWBIND

Gibt an, ob eine DLL gebunden werden kann.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Hinweise

Die **/ALLOWBIND** Option legt ein bit im Header einer DLL ein, das Bind.exe zeigt an, dass das Image darf gebunden werden soll. Bindung können ein Bild schneller zu laden, wenn das Ladeprogramm keine REBASE ausführen, und führen Sie die Adresse Fixup für jede DLL-Datei auf die verwiesen wird. Möglicherweise möchten Sie keine DLL gebunden wird, wenn sie digital signiert wurde — Bindung macht die Signatur ungültig. Bindung hat keine Auswirkungen, wenn Adresse Space Layout Randomization (ASLR) für das Image aktiviert ist, mithilfe von **/DynamicBase** in Versionen von Windows, die ASLR unterstützen.

Verwendung **/ALLOWBIND: No** um zu verhindern, dass Bind.exe binden die DLL.

Weitere Informationen finden Sie unter den [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) -Linkeroption.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)