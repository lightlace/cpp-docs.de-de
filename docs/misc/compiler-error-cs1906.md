---
title: "Compilerfehler CS1906"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS1906"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1906"
ms.assetid: 1a6abf5c-f673-4256-93ac-313dce50acc0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1906
Ungültige Option "Option"; Ressourcensichtbarkeit muss entweder "public" oder "private" sein.  
  
 Dieser Fehler kennzeichnet eine ungültige [\/resource \(Ressourcendatei in Ausgabe einbetten\)](../Topic/-resource%20\(C%23%20Compiler%20Options\).md)\- oder [\/linkresource \(mit .NET Framework\-Ressource verknüpfen\)](../Topic/-linkresource%20\(C%23%20Compiler%20Options\).md)\-Befehlszeilenoption. Überprüfen Sie die Syntax der **\/resource**\- oder **\/linkresource**\-Befehlszeilenoption, und stellen Sie sicher, dass der verwendete Zugriffsmodifizierer entweder **public** oder `private` ist.