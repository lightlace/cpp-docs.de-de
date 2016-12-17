---
title: "/ALLOWBIND"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALLOWBIND (editbin-Option)"
  - "/ALLOWBIND (editbin-Option)"
  - "-ALLOWBIND (editbin-Option)"
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /ALLOWBIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob eine DLL gebunden werden kann.  
  
```  
  
/ALLOWBIND[:NO]  
  
```  
  
## Hinweise  
 Die **\/ALLOWBIND** \- Option legt ein Bit im Header einer DLL ab, die zu Bind.exe angibt, dass das Bild ermöglicht wird gebunden werden.  Das Binden kann ein Bild zur Auslastung schneller ermöglichen, wenn das Ladeprogramm für jede Adressenfixups Referenz\-DLL nicht umbasieren und ausführen muss.  Sie sollten eine DLL nicht gebunden werden, wenn das SignierteBindung ungültig macht die Signatur war.  Das Binden hat keine Auswirkungen, wenn Adressbereichslayoutzufallszuteilung \(ASLR\) für die Anwendung aktiviert ist, indem Sie **\/DYNAMICBASE** auf Versionen von Windows verwendet, die ASLR unterstützen.  
  
 Verwenden Sie **\/ALLOWBIND:NO**, um zu verhindern, dass die DLL Bind.exe bindet.  
  
 Weitere Informationen finden Sie die Linkeroption [\/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md).  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)