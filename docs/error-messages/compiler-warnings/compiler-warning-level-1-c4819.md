---
title: "Compilerwarnung (Stufe 1) C4819"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4819"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4819"
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4819
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Datei enthält ein Zeichen, das in der aktuellen Codepage \(Nummer\) nicht dargestellt werden kann.Speichern Sie die Datei im Unicode\-Format, um Datenverluste zu vermeiden.  
  
 C4819 tritt auf, wenn eine ANSI\-Quelldatei auf einem System mit einer Codepage kompiliert wird, die nicht alle Zeichen in der Datei darstellen kann.  
  
 Um C4819 zu beheben, speichern Sie die Datei im Unicode\-Format.  Wählen Sie in Visual Studio **Datei**, **Erweiterte Speicheroptionen** aus.  Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** eine Codierung, die alle Zeichen in der Datei darstellen kann, z. B. UTF\-8, und wählen Sie dann **OK**.