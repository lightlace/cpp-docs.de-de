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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92309c9299303429c61f84911e180468f6354475
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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