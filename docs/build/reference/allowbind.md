---
title: -ALLOWBIND | Microsoft Docs
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
ms.openlocfilehash: af4a9f3d898d0087f0e8e861ccfe72e4adadb1de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368914"
---
# <a name="allowbind"></a>/ALLOWBIND
Gibt an, ob eine DLL gebunden werden kann.  
  
```  
  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **/ALLOWBIND** Option legt ein bit in einem DLL-Header, das Bind.exe angezeigt wird, dass das Bild zu bindenden zulässig ist. Bindung können ein Bild schneller zu laden, wenn das Ladeprogramm keine rebase, und führen Sie die Adresse Fixup für jede DLL-Datei verwiesen wird. Möglicherweise möchten Sie keine DLL gebunden wird, wenn sie digital signiert wurde – Bindung macht die Signatur ungültig. Bindung hat keine Auswirkungen, wenn Adresse Space Layout Randomization (ASLR) für das Bild aktiviert ist, mit **"/ DynamicBase"** auf Versionen von Windows, die ASLR unterstützen.  
  
 Verwendung **/ALLOWBIND: No** um zu verhindern, dass Bind.exe binden die DLL.  
  
 Weitere Informationen finden Sie unter der [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) (Linkeroption).  
  
## <a name="see-also"></a>Siehe auch  
 [EDITBIN-Optionen](../../build/reference/editbin-options.md)