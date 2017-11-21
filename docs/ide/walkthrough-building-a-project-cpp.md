---
title: 'Exemplarische Vorgehensweise: Erstellen eines Projekts (C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- building projects [C++]
- projects [C++], building
- project building [C++]
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 713a74cc889721259ca99f1622ef5e9919edf573
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-building-a-project-c"></a>Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)
In dieser exemplarischen Vorgehensweise fügen Sie absichtlich einen Visual C++-Syntaxfehler in den Code ein, um zu lernen, wie ein Kompilierungsfehler aussieht und wie Sie diesen beheben. Beim Kompilieren des Projekts wird eine Fehlermeldung angezeigt. Diese gibt an, worin das Problem besteht und wo es aufgetreten ist.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
-   Außerdem wird angenommen, dass Sie zuvor verwandten exemplarischen Vorgehensweisen abgeschlossen haben, die aufgelisteten [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-compilation-errors"></a>So beheben Sie Kompilierungsfehler  
  
1.  Löschen Sie das Semikolon in der letzten Zeile von TestGames.cpp, sodass diese Zeile ungefähr wie folgt aussieht:  
  
     `return 0`  
  
2.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
3.  Eine Nachricht in die **Fehlerliste** Fenster gibt an, dass bei der Erstellung des Projekts ein Fehler aufgetreten. Die Beschreibung sieht ungefähr so aus:  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     Markieren Sie zum Anzeigen von Hilfeinformationen zu diesem Fehler erhalten sie in der **Fehlerliste** Fenster und wählen Sie dann die F1-Taste.  
  
4.  Fügen Sie das Semikolon wieder am Ende der Zeile mit dem Syntaxfehler ein:  
  
     `return 0;`  
  
5.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
     Eine Nachricht in die **Ausgabe** Fenster gibt an, dass das Projekt ordnungsgemäß kompiliert.  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Game.vcxproj -> C:\Users\<username>\Documents\Visual Studio <version>\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
    ```  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Vorherige:** [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **Weiter:**[Exemplarische Vorgehensweise: Testen eines Projekts (C++)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)