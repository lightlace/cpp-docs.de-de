---
title: "/INTEGRITYCHECK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/INTEGRITYCHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INTEGRITYCHECK editbin-Optionen"
  - "INTEGRITYCHECK editbin-Optionen"
  - "-INTEGRITYCHECK editbin-Optionen"
ms.assetid: 2a293705-4396-421b-a5a5-693b4b867a85
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /INTEGRITYCHECK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die digitale Signatur des Binärimages zur Ladezeit überprüft werden muss.  
  
```  
  
/INTEGRITYCHECK[:NO]  
  
```  
  
## Hinweise  
 Mit dieser Option wird im Header der DLL\-Datei oder der ausführbaren Datei ein Flag festgelegt, das eine Überprüfung der digitalen Signatur mithilfe des Speicher\-Managers erfordert, um das Image in Windows zu laden.  Windows\-Versionen vor Windows Vista ignorieren dieses Flag.  Diese Option muss für 64\-Bit\-DLLs festgelegt werden, die den Kernelmoduscode implementieren, und wird für alle Gerätetreiber empfohlen.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Kernelmodus\-Codesignaturen](http://go.microsoft.com/fwlink/?linkid=237093) auf der MSDN\-Website.  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)