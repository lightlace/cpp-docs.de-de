---
title: Verteilen von ATL-Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c824dd4ae174a4418c6744e592dd62dc54b9595
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326383"
---
# <a name="redistributing-an-atl-application"></a>Verteilen von ATL-Anwendungen
Ab Visual Studio 2012 ist die Active Template Library (ATL) eine reine Headerbibliothek. ATL-Projekte verfügen nicht über die Option „Dynamischer Link zu ATL“. Es ist keine verteilbare ATL-Bibliothek erforderlich.  
  
 Möchten Sie eine ausführbare ATL-Anwendung weiterverteilen, müssen Sie die EXE-Datei (sowie alle darin enthaltenen Steuerelemente) registrieren, indem Sie den folgenden Befehl ausgeben:  
  
```  
filename /regserver  
```  
  
 Hierbei steht `filename` für den Namen der ausführbaren Datei.  
  
 In Visual Studio 2010 kann ein ATL-Projekt für eine MinDependency- oder MinSize-Konfiguration erstellt werden. Eine MinDependency-Konfiguration erhalten Sie, wenn Sie auf der Eigenschaftenseite **Allgemein** die Eigenschaft **Verwendung von ATL** auf **Statische Verknüpfung zu ATL** und auf der Eigenschaftenseite **Codegenerierung** (Ordner C/C++) die Eigenschaft **Laufzeitbibliothek** auf **Multithreaded (/MT)** festlegen.  
  
 Eine MinSize-Konfiguration erhalten Sie, wenn Sie auf der Eigenschaftenseite **Allgemein** die Eigenschaft **Verwendung von ATL** auf **Dynamische Verknüpfung zu ATL** festlegen oder auf der Eigenschaftenseite **Codegenerierung** (Ordner C/C++) die Eigenschaft **Laufzeitbibliothek** auf **Multithreaded-DLL (/MD)** festlegen.  
  
 Mit MinSize wird die Ausgabedatei so klein wie möglich gehalten, allerdings müssen hierfür „ATL100.dll“ und „Msvcr100.dll“ auf dem Zielcomputer vorhanden sein (falls die Option **Multithreaded-DLL (/MD)** ausgewählt wurde). ATL100.dll muss auf dem Zielcomputer registriert sein, um sicherzustellen, dass alle ATL-Funktionen zur Verfügung stehen. ATL100.dll enthält ANSI- und Unicode-Exporte.  
  
 Wenn Sie ein ATL- oder OLE DB-Vorlagenprojekt mit MinDependency als Ziel erstellen, müssen Sie ATL100.dll auf dem Zielcomputer nicht installieren und registrieren, obwohl dies zu einem größeren Programmimage führen kann.  
  
 Möchten Sie eine ausführbare ATL-Anwendung weiterverteilen, müssen Sie die EXE-Datei (sowie alle darin enthaltenen Steuerelemente) registrieren, indem Sie den folgenden Befehl ausgeben:  
  
```  
filename /regserver  
```  
  
 Hierbei steht `filename` für den Namen der ausführbaren Datei.  
  
 Bei OLE DB-Vorlagenanwendungen stellen Sie sicher, dass auf dem Zielcomputer die aktuellen Versionen der MDAC (Microsoft Data Access Components)-Dateien vorhanden sind. Weitere Informationen finden Sie unter [Redistributing Database Support Files (Verteilen von Datenbankunterstützungsdateien)](../ide/redistributing-database-support-files.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)