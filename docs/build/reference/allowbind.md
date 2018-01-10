---
title: -ALLOWBIND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /allowbind
dev_langs: C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4cbd5c619b0a9e146adb9a8ec9117f59e01b89d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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