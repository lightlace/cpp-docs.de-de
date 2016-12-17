---
title: ".FPO"
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
  - ".FPO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".FPO directive"
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# .FPO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die .FPO\-Direktive steuern die Ausgabe von Datensätzen Debuggen auf dem .debug$F\-Segment oder \- Abschnitt.  
  
## Syntax  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### Parameter  
 `cdwLocals`  
 Zahl, lokale Variablen ein Wert des Bits 32 ohne Vorzeichen.  
  
 `cdwParams`  
 Größe der Parameter in den DWORDEN, ein Wert des Bits 16 ohne Vorzeichen.  
  
 *cbProlog*  
 Die Anzahl der Bytes im Code einleitungs Funktion, der Wert des Bits 8 ohne Vorzeichen.  
  
 `cbRegs`  
 Zahlenregister gespeichert.  
  
 `fUseBP`  
 Gibt an, ob das EBP\-Register zugeordnet wurde.  0 oder 1.  
  
 *cbFrame*  
 Gibt den Typ des Rahmens an.  Weitere Informationen finden Sie unter [FPO\_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352).  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)