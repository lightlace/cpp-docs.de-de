---
title: "Isolierung der MFC-Bibliothek f&#252;r Standardsteuerelemente"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, Common Controls-Bibliothek"
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Isolierung der MFC-Bibliothek f&#252;r Standardsteuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Bibliothek für allgemeine Steuerelemente wird jetzt in MFC isoliert und verschiedene Module \(z Benutzer DLLs\) um unterschiedliche Versionen der Bibliothek für allgemeine Steuerelemente zu verwenden, indem die Version in ihren Manifesten angibt.  
  
 Eine MFC\-Anwendung \(oder der Benutzercode aufgerufen von MFC\) macht Aufrufe der Bibliothek für allgemeine Steuerelementes\-APIs Wrapper von Funktionen mit dem Namen `Afx`*FunctionName*, wobei *FunctionName* der Name einer API der gängigen Steuerelementen ist.  Diese werden in afxcomctl32.h Wrapperfunktionen und in afxcomctl32.inl definiert.  
  
 Sie können die [AFX\_COMCTL32\_IF\_EXISTS](../Topic/AFX_COMCTL32_IF_EXISTS.md) und [AFX\_COMCTL32\_IF\_EXISTS2](../Topic/AFX_COMCTL32_IF_EXISTS2.md)\-Makros verwenden \(in afxcomctl32.h\), um zu bestimmen, ob die Bibliothek für allgemeine Steuerelemente eine bestimmte API implementiert, anstatt, [GetProcAddress](../build/getprocaddress.md) aufzurufen.  
  
 Technisch machen Sie Aufrufe der Bibliothek für allgemeine Steuerelementes\-APIs durch eine Wrapperklasse, `CComCtlWrapper` \(definiert in afxcomctl32.h\).  `CComCtlWrapper` ist ebenfalls für das Laden und Entladen von comctl32.dll zuständig.  Der MFC\-Modulzustand enthält einen Zeiger auf eine Instanz von `CComCtlWrapper`.  Sie können auf die Wrapperklasse mithilfe des Makros `afxComCtlWrapper` zugreifen.  
  
 Beachten Sie, dass der aufrufende API allgemeinen Steuerelemente direkt \(ohne Verwendung des MFC\-Wrappers funktioniert\), von einer MFC\-Anwendung oder Benutzer aus einer DLL in den meisten Fällen funktioniert, da die MFC\-Anwendung oder die Benutzer der Bibliothek DLL für allgemeine Steuerelemente gebunden wird, Anwendungstest sie in ihrem Manifest\) an.  Allerdings muss der MFC\-Code selbst die Wrapper verwenden, da MFC\-Code kann von Benutzer DLLs mit verschiedenen Bibliothek für allgemeine Steuerelementes\-Versionen aufgerufen wird.