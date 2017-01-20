---
title: "Globale Funktionen des Compiler-COM"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, COM-Unterstützung"
  - "COM, Compilerunterstützung"
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Globale Funktionen des Compiler-COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die folgenden Routinen sind verfügbar:  
  
|Funktion|Beschreibung|  
|--------------|------------------|  
|[\_com\_raise\_error](../cpp/com-raise-error.md)|Löst einen [\_com\_error](../cpp/com-error-class.md) als Reaktion auf einen Fehler aus.|  
|[\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)|Ersetzt die Standardfunktion für die COM\-Fehlerbehandlung.|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Konvertiert einen `BSTR`\-Wert in einen **char \***.|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Konvertiert einen **char \***\-Wert in einen `BSTR`.|  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Compilerklassen für COM\-Unterstützung](../cpp/compiler-com-support-classes.md)   
 [COM\-Unterstützung des Compilers](../cpp/compiler-com-support.md)