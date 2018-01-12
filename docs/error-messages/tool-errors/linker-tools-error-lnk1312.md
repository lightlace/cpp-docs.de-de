---
title: Linkertoolfehler Lnk1312 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1312
dev_langs: C++
helpviewer_keywords: LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d7f7b57512f58402403a50bf57176f975769573
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1312"></a>Linkertoolfehler LNK1312
Ungültige oder beschädigte Datei: Assembly konnte nicht importiert  
  
 Beim Erstellen einer Assembly, die einer Datei, ein Modul oder eine Assembly kompiliert mit **"/ CLR"** wurde übergeben, um die **ASSEMBLYMODULE** (Linkeroption).  Wenn Sie eine Objektdatei zu übergeben **ASSEMBLYMODULE**, übergeben Sie das Objekt direkt an dem Linker nicht an **ASSEMBLYMODULE**.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel erstellt die OBJ-Datei.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird LNK1312 generiert.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```