---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 8f59cc83c06bbaaccba911c44835247253cb264b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416890"
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
