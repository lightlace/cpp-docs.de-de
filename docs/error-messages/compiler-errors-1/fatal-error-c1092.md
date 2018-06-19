---
title: Schwerwiegender Fehler C1092 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8f5b5d903fe1fb2d3182a7b08f7bf82ddf334fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199248"
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