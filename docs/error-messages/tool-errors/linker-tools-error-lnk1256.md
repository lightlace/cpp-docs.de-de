---
title: "Linkertoolfehler LNK1256"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "xml"
  - "LNK1256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1256"
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler bei ALINK\-Operation: Ursache  
  
 Ein häufiger Grund für LNK1256 ist eine falsche Versionsnummer für eine Assembly.  Der Wert 65535 ist für keinen Teil der Assemblyversionsnummer zulässig.  Der gültige Bereich für Assemblyversionen ist 0 – 65534.  
  
 LNK1256 kann auch entstehen, wenn ALINK den benannten Schlüsselcontainer nicht finden konnte.  Löschen Sie den Schlüsselcontainer und fügen Sie ihn erneut denCSP für starke Namen mit Hilfe von [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) hinzu  
  
 Ein weiterer Grund für LNK1256 ist ein Versionskonflikt zwischen dem Linker und Alink.dll.  Dies kann durch eine fehlerhafte Installation von Visual Studio verursacht werden.  Verwenden Sie **Programme und Funktionen** in der Windows\-Systemsteuerung, um Visual Studio zu reparieren oder neu zu installieren.  
  
 Im folgende Beispiel wird LNK1256 generiert:  
  
```  
// LNK1256.cpp  
// compile with: /clr /LD  
// LNK1256 expected  
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];  
public class CMyClass {  
public:  
   int value;  
};  
```