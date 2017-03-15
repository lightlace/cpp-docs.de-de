---
title: Schwerwiegender Fehler C1092 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 6d93fd662b638126e21d5f5f034138c0e6f0e0ad
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1092"></a>Schwerwiegender Fehler C1092
Bearbeiten und Fortfahren unterstützt keine Änderungen an Datentypen. Build erforderlich  
  
 Geändert oder einen Datentyp seit dem letzten erfolgreichen Build hinzugefügt.  
  
-   Bearbeiten und Fortfahren unterstützt keine Änderungen an vorhandenen Datentypen, einschließlich Klasse, Struktur oder Enumeration Definitionen. Sie müssen den Debugvorgang unterbrechen und erstellen Sie die Anwendung.  
  
-   Bearbeiten und Fortfahren unterstützt nicht das Hinzufügen neuer Datentypen, wenn eine Programm-Datenbankdatei, beispielsweise vc*x*0 Pdb (wobei *x* ist die Hauptversion von Visual C++ verwendet) ist schreibgeschützt. Um Daten hinzuzufügen, muss der Compiler die PDB-Datei im Schreibmodus öffnen.  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Um diesen Fehler zu entfernen, ohne die aktuelle Debugsitzung zu beenden  
  
1.  Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.  
  
2.  Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen**aus.  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>So entfernen Sie diesen Fehler, ohne den Quellcode zu ändern  
  
1.  Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.  
  
2.  Wählen Sie im Menü **Erstellen** den Befehl **Erstellen**aus.  
  
 Weitere Informationen finden Sie unter der [unterstützte Codeänderungen](/visualstudio/debugger/supported-code-changes-cpp).
