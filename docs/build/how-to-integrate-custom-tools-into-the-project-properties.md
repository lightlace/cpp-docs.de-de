---
title: 'Vorgehensweise: Integrieren von benutzerdefinierte Tools in den Projekteigenschaften | Microsoft Docs'
ms.custom: 
ms.date: 04/27/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msbuild.cpp.howto.integratecustomtools
dev_langs: C++
helpviewer_keywords: 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 128b19c1175fb5f39599a9ccaeae66d1fc53fdab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Gewusst wie: Integrieren von benutzerdefinierte Tools in die Projekteigenschaften
Sie können Optionen für benutzerdefinierte Tools in Visual Studio hinzufügen **Eigenschaftenseiten** Fenster durch das Erstellen einer zugrunde liegenden XML-Schemadatei.  
  
 Die **Konfigurationseigenschaften** Teil der **Eigenschaftenseiten** Fenster wird angezeigt, die als bekanntermaßen Einstellungsgruppen *Regeln*. Jede Regel enthält die Einstellungen für ein Tool oder eine Gruppe von Funktionen. Z. B. die **Linker** Regel enthält die Einstellungen für den Linkertool. Die Einstellungen in einer Regel können unterteilt *Kategorien*.  
  
 Dieses Dokument erläutert, wie Sie eine Datei in einem Set-Verzeichnis zu erstellen, die Eigenschaften für ein eigenes Tool enthält, sodass die Eigenschaften beim Start von Visual Studio geladen werden. Informationen zum Ändern der Datei finden Sie unter [Plattform Erweiterbarkeit Teil 2](http://go.microsoft.com/fwlink/?LinkID=191489) im Visual Studio-Projekt-Team-Blog.  
  
### <a name="to-add-or-change-project-properties"></a>Hinzufügen oder Ändern von Projekteigenschaften  
  
1.  Erstellen Sie eine XML-Datei, in der XML-Editor.  
  
2.  Speichern Sie die Datei in Visual Studio-2017 `VCTargets\1033` Ordner. Sie müssen einen anderen Pfad für jede Edition von Visual Studio-2017, die installiert ist und jede Sprache. Beispielsweise ist der Pfad des Ordners für Visual Studio Enterprise Edition auf Englisch `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Passen Sie den Pfad für Ihre Sprache und die Visual Studio-Edition an. Jede Regel in der **Eigenschaftenseiten** Fenster wird durch eine XML-Datei in diesem Ordner dargestellt. Stellen Sie sicher, dass die Datei im Ordner eindeutig benannt ist.  
  
3.  Kopieren Sie den Inhalt des `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`, schließen Sie es ohne Änderungen zu speichern, und fügen Sie den Inhalt in der neuen XML-Datei. Sie können XML-Schemadatei – Dies ist nur eine, die verwendet werden können, damit Sie mit einer Vorlage starten.  
  
4.  Ändern Sie den Inhalt entsprechend Ihren Anforderungen, in die neue XML-Datei. Stellen Sie sicher, dass die **Regelname** und **Rule.DisplayName** am Anfang der Datei.  
  
5.  Speichern Sie die Änderungen zu und schließen Sie die Datei.  
  
6.  Die XML-Dateien im `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` beim Start von Visual Studio geladen werden. Aus diesem Grund, um die neue Datei zu testen, starten Sie Visual Studio neu.  
  
7.  In **Projektmappen-Explorer**mit der rechten Maustaste auf ein Projekt, und klicken Sie dann auf **Eigenschaften**. In der **Eigenschaftenseiten** im linken Bereich des Fensters stellen Sie sicher, dass ein neuer Knoten mit dem Namen der Regel vorhanden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
