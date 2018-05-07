---
title: Linkertoolfehler Lnk1256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e4039dccb4dc8abd421b4622bbe928931f7f396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1256"></a>Linkertoolfehler LNK1256
Fehler bei ALINK-Operation: Ursache  
  
 Ein häufiger Grund für LNK1256 ist eine falsche Versionsnummer für eine Assembly. Der Wert 65535 ist für keinen Teil der Assemblyversionsnummer zulässig. Der gültige Bereich für Assemblyversionen ist 0 – 65534.  
  
 LNK1256 kann auch entstehen, wenn ALINK den benannten Schlüsselcontainer nicht finden konnte. Container für den Schlüssel löschen und erneut hinzufügen zum CSP für starke Namen mit [Sn.exe (Strong Name-Tool)](/dotnet/framework/tools/sn-exe-strong-name-tool).  
  
 Ein weiterer Grund für LNK1256 ist ein Versionskonflikt zwischen dem Linker und Alink.dll. Dies kann durch eine fehlerhafte Installation von Visual Studio verursacht werden. Verwendung **Programme und Funktionen** in der Windows-Systemsteuerung reparieren oder neu installieren von Visual Studio.  
  
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