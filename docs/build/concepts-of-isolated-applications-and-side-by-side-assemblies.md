---
title: Konzept der isolierten Anwendungen und Seite-an-Seite-Assemblys | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- side-by-side assemblies [C++]
- isolated assemblies [C++]
ms.assetid: 945a885f-cb3e-4c8a-a0b9-2c2e3e02cc50
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9166f62c51344cc9c620da34d9c6fcee4665f400
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="concepts-of-isolated-applications-and-side-by-side-assemblies"></a>Konzept der isolierten Anwendungen und der parallelen Assemblys
Eine Anwendung wird als [isolierte Anwendung](http://msdn.microsoft.com/library/aa375190) angesehen, wenn alle ihre Komponenten [parallele Assemblys](http://msdn.microsoft.com/library/ff951640)sind. Eine parallele Assembly ist eine Ansammlung von Ressourcen, z. B. eine Gruppe von DLLs, Windows-Klassen, COM-Servern, Typbibliotheken oder Schnittstellen, die zusammen entwickelt wurden und einer Anwendung zur Laufzeit zur Verfügung gestellt werden. Im Normalfall besteht eine parallele Assembly aus einer oder mehreren DLLs.  
  
## <a name="shared-or-private"></a>Freigegeben oder privat  
 Eine parallele Assembly kann entweder freigegeben oder privat sein. [Freigegebene parallele Assemblys](https://msdn.microsoft.com/en-us/library/aa375996.aspx) können von mehreren Anwendungen verwendet werden, die in ihren Manifesten eine Abhängigkeit von der Assembly angeben. Verschiedene Anwendungen, die zur selben Zeit ausgeführt werden, können mehrere Versionen paralleler Assemblys verwenden. Eine [private Assembly](http://msdn.microsoft.com/library/ff951638) ist eine Assembly, die zusammen mit einer Anwendung bereitgestellt wird und nur dieser Anwendung für den exklusiven Zugriff zur Verfügung steht. Private Assemblys werden in dem Ordner, der die ausführbare Datei der Anwendung enthält, oder in einem seiner Unterordner installiert.  
  
## <a name="manifests-and-search-order"></a>Manifeste und Suchreihenfolge  
 Sowohl isolierte Anwendungen als auch parallele Assemblys werden von [Manifesten](http://msdn.microsoft.com/library/aa375365)beschrieben. Ein Manifest ist ein XML-Dokument, das entweder als externe Datei vorliegt oder als Ressource in einer Anwendung oder Assembly eingebettet ist. Die Manifestdatei einer isolierten Anwendung wird zur Verwaltung der Namen und Versionen freigegebener paralleler Assemblys verwendet, an die die Anwendung zu Laufzeit gebunden werden muss. Das Manifest einer parallelen Assembly gibt den Namen, die Versionen, die Ressourcen sowie abhängige Assemblys der parallelen Assembly an. Das Manifest einer freigegebenen parallelen Assembly wird im Ordner %WINDIR%\WinSxS\Manifests\ installiert. Bei privaten Assemblys empfiehlt es sich, das Manifest als Ressource mit der ID 1 in die DLL einzubeziehen. Sie können der privaten Assembly und der DLL auch denselben Namen geben. Weitere Informationen finden Sie unter [Private Assemblys](http://msdn.microsoft.com/library/ff951638).  
  
 Zur Ausführungszeit verwendet Windows die Assemblyinformationen aus dem Anwendungsmanifest zur Suche und zum Laden der entsprechenden parallelen Assembly. Wenn eine isolierte Anwendung eine Assemblyabhängigkeit angibt, sucht das Betriebssystem zuerst unter den freigegebenen Assemblys im systemeigenen Assemblycache im Ordner %WINDIR%\WinSxS\ nach der betreffenden Assembly. Wenn die benötigte Assembly nicht gefunden werden kann, sucht das Betriebssystem anschließend in der Ordnerstruktur des Anwendungsverzeichnisses nach einer privaten Assembly. Weitere Informationen finden Sie unter [Assemblysuchsequenz](http://msdn.microsoft.com/library/aa374224).  
  
## <a name="changing-dependencies"></a>Ändern von Abhängigkeiten  
 Die Abhängigkeiten von parallelen Assemblys können nach der Bereitstellung einer Anwendung mithilfe von [Herausgeberkonfigurationsdateien](http://msdn.microsoft.com/library/aa375682) und [Anwendungskonfigurationsdateien](http://msdn.microsoft.com/library/aa374182)geändert werden. Eine Herausgeberkonfigurationsdatei, auch Herausgeberrichtliniendatei genannt, ist eine XML-Datei, mit der Anwendungen und Assemblys global von der Verwendung einer Version einer parallelen Assembly auf die Verwendung einer anderen Version derselben Assembly umgeleitet werden können. Sie können eine Abhängigkeit z. B. bei der Bereitstellung einer Fehlerkorrektur oder eines Sicherheitsupdates für eine parallele Assembly ändern, wenn Sie alle Anwendungen so umleiten möchten, dass sie die korrigierte Version verwenden. Eine Anwendungskonfigurationsdatei ist eine XML-Datei, die eine bestimmte Anwendung von der Verwendung einer Version einer parallelen Assembly auf eine andere zu verwendende Version derselben Assembly umleitet. Verwenden Sie eine Anwendungskonfigurationsdatei, um eine bestimmte Anwendung so umzuleiten, dass sie eine andere Version einer parallelen Assembly verwendet als in der Herausgeberkonfigurationsdatei angegeben wurde. Weitere Informationen finden Sie unter [Konfiguration](http://msdn.microsoft.com/library/aa375123).  
  
## <a name="visual-c-libraries"></a>Visual C++-Bibliotheken  
 In Visual Studio 2005 und Visual Studio 2008 wurden verteilbare Bibliotheken wie ATL, MRC, CRT, die C++-Standardbibliothek, OpenMP und MSDIA als freigegebene parallele Assemblys im systemeigenen Assemblycache bereitgestellt. In der aktuellen Version werden die verteilbaren Bibliotheken zentral bereitgestellt. Standardmäßig enthalten alle mit Visual C++ erstellten Anwendungen ein in die endgültige Binärdatei eingebettetes Manifest, das die Abhängigkeiten dieser Binärdatei von den Visual C++-Bibliotheken beschreibt. Weitere Informationen zum Verständnis der Manifestgenerierung für Visual C++-Anwendungen finden Sie unter [Understanding Manifest Generation for C/C++ Programs](../build/understanding-manifest-generation-for-c-cpp-programs.md). Für Anwendungen, die statisch mit den verwendeten Bibliotheken verknüpft sind, oder für lokal bereitgestellte Anwendungen ist kein Manifest erforderlich. Weitere Informationen zur Bereitstellung finden Sie unter [Deployment in Visual C++](../ide/deployment-in-visual-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)