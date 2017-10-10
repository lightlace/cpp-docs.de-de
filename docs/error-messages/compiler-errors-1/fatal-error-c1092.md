---
title: Schwerwiegender Fehler C1092 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fac0a5218e1faf16d3db459567c36775acd9bb12
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1092"></a>Schwerwiegender Fehler C1092
Bearbeiten und Fortfahren unterstützt keine Änderungen an Datentypen. Build erforderlich  
  
 Geändert oder einen Datentyp seit dem letzten erfolgreichen Build hinzugefügt wurden.  
  
-   Bearbeiten und Fortfahren unterstützt keine Änderungen an vorhandenen Datentypen, einschließlich Klasse, Struktur oder Enumeration Definitionen. Sie müssen den Debugvorgang unterbrechen und die Anwendung zu erstellen.  
  
-   Bearbeiten und Fortfahren unterstützt nicht das Hinzufügen von neuen Datentypen, wenn eine Programmdatenbankdatei, z. B. vc*x*0 Pdb (wobei *x* die Hauptversion von Visual C++ verwendet wird) ist schreibgeschützt. Um Datentypen hinzuzufügen, muss der Compiler die PDB-Datei im Schreibmodus öffnen.  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Um diesen Fehler zu entfernen, ohne die aktuelle Debugsitzung zu beenden  
  
1.  Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.  
  
2.  Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen**aus.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>So entfernen Sie diesen Fehler, ohne den Quellcode zu ändern  
  
1.  Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.  
  
2.  Wählen Sie im Menü **Erstellen** den Befehl **Erstellen**aus.  
  
 Weitere Informationen hierzu finden Sie unter [Unterstützte Codeänderungen](/visualstudio/debugger/supported-code-changes-cpp).
