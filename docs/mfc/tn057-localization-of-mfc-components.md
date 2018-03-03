---
title: 'TN057: Lokalisierung von MFC-Komponenten | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.components
dev_langs:
- C++
helpviewer_keywords:
- components [MFC], localizing
- TN057
- resources [MFC], localization
- localization [MFC], MFC resources
- localization [MFC], MFC components
- MFC DLLs [MFC], localizing
- DLLs [MFC], localizing MFC
- localization [MFC], resources
ms.assetid: 5376d329-bd45-41bd-97f5-3d895a9a0af5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e27b737a76b30e7193a9afb7797a20951294032e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: Lokalisierung von MFC-Komponenten
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt einige der entwirft und Vorgehensweisen enthalten, die Sie zum Lokalisieren von der Komponentennamens verwenden können, wenn sie eine Anwendung oder ein OLE-Steuerelement oder eine DLL, die MFC verwendet.  
  
## <a name="overview"></a>Übersicht  
 Es sind eigentlich zwei Probleme beim Auflösen Lokalisieren von einer Komponente, die MFC verwendet. Zunächst müssen Sie Ihre eigenen Ressourcen lokalisieren – Zeichenfolgen, Dialogfelder und andere Ressourcen, die an die Komponente spezifisch sind. Die meisten Komponenten auch mithilfe von MFC erstellt und verwenden eine Reihe von Ressourcen, die von MFC definiert sind. Sie müssen auch lokalisierte MFC-Standardressourcen angeben. Glücklicherweise werden mehrere Sprachen, von MFC selbst bereits bereitgestellt.  
  
 Darüber hinaus sollte die Komponente vorbereitet werden, in die zielumgebung (Europäische oder DBCS-fähigen Umgebung) ausgeführt. Meistens, hängt dies Ihre Anwendung mit dem Satz high-Bit-Zeichen ordnungsgemäß behandeln und Behandlung von Zeichenfolgen mit Doppelbyte-Zeichen. MFC ist, wird standardmäßig für beide Umgebungen, aktiviert, es ist möglich, eine Binärdatei weltweite verfügen, die auf allen Plattformen mit nur verschiedene Ressourcen, die beim Setup Netzbetrieb verwendet wird.  
  
## <a name="localizing-your-components-resources"></a>Lokalisieren von Ressourcen der Komponente  
 Lokalisieren von Ihrer Anwendung oder DLL sollten umfassen ersetzen einfach die Ressourcen mit Ressourcen, die der Zielsprache entsprechen. Für Ihre eigenen Ressourcen, ist dies relativ einfach: die Ressourcen im Ressourcen-Editor bearbeiten und die Anwendung erstellen. Wenn der Code ordnungsgemäß geschrieben wird, dass es werden keine Zeichenfolgen oder Text, den Sie hartcodierte in Ihren C++-Quellcode lokalisieren möchten - alle Lokalisierung möglich durch Ressourcen einfach ändern. Tatsächlich können Sie Ihrer Komponente implementieren, sodass alle Bereitstellen einer lokalisierten Version keine selbst einen Build des ursprünglichen Codes beinhaltet. Dies ist sehr komplex, jedoch lohnt es und ist der Mechanismus zum MFC selbst ausgewählt. Es ist auch möglich, eine Anwendung zu lokalisieren, indem Sie die EXE- oder DLL-Datei in der Ressourcen-Editor zu laden und die Ressourcen direkt zu bearbeiten. Zwar möglich erfordert sie die erneute Anwendung dieser Änderungen jedes Mal, wenn Sie eine neue Version der Anwendung erstellen.  
  
 Eine Möglichkeit, dies zu vermeiden ist, alle Ressourcen in einer separaten DLL, bezeichnet die Satelliten-DLL zu finden. Diese DLL-Datei wird dann zur Laufzeit dynamisch geladen und die Ressourcen werden von dieser DLL anstatt vom Hauptmodul für den gesamten Code geladen. Dieser Ansatz wird von MFC direkt unterstützt. Erwägen Sie eine Anwendung mit dem Namen "MyApp". EXE-DATEI; Es konnte aller zugehörigen Ressourcen befindet sich in einer DLL MYRES aufgerufen haben. DLL. In der Anwendungsverzeichnis `InitInstance` würden sie Folgendes ein, um die DLL zu laden und dazu führen, dass MFC ermöglicht, Ressourcen von diesem Speicherort geladen ausführen:  
  
```  
CMyApp::InitInstance()  
{ *// one of the first things in the init code  
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)  
    AfxSetResourceHandle(hInst);

 *// other initialization code would follow  
 .  
 .  
 .  
}  
```  
  
 MFC wird von nun an werden Ressourcen aus dieser DLL anstelle von myapp.exe geladen werden. Alle Ressourcen müssen sich aber in dieser DLL vorhanden sein; Die Anwendungsinstanz, um eine bestimmte Ressource durchsucht MFC nicht. Dieses Verfahren gilt gleichermaßen gut für normale MFC-DLLs sowie von OLE-Steuerelementen. Das Setupprogramm kopieren die entsprechende Version von MYRES. DLL abhängig von der Ressource Gebietsschema möchte der Benutzer.  
  
 Es ist relativ leicht, erstellen Sie eine Ressource nur DLL. Erstellen Sie ein DLL-Projekt, fügen Sie Ihrer. RC-Datei, und fügen Sie die erforderlichen Ressourcen. Wenn Sie ein vorhandenes Projekt, das diese Technik nicht verwendet verfügen, können Sie die Ressourcen aus diesem Projekt kopieren. Nach dem Hinzufügen der Ressourcendatei für das Projekt, sind Sie fast bereit, um das Projekt zu erstellen. Das einzige notwendig, wird der Linker Optionen umfassen festlegen, um **/NOENTRY**. Dies weist den Linker an, dass die DLL kein Einstiegspunkt - aufweist, da es keinen Code enthält, verfügt er über keinen Einstiegspunkt.  
  
> [!NOTE]
>  Der Ressourcen-Editor in Visual C++ 4.0 und höher unterstützt mehrere Sprachen pro. RC-Datei. Dies kann sehr einfach, die Lokalisierung in einem einzelnen Projekt verwalten erleichtern. Die Ressourcen für jede Sprache werden von Präprozessordirektiven, die von der Ressourcen-Editor generierten gesteuert.  
  
## <a name="using-the-provided-mfc-localized-resources"></a>Die angegebene MFC-Bibliothek mit lokalisierten Ressourcen  
 Alle MFC-Anwendung, die Sie erstellen verwendet zwei Dinge von MFC: Code und Ressourcen. Das verfügt über MFC verschiedene Fehlermeldungen, integrierte Dialogfelder und anderen Ressourcen, die von der MFC-Klassen verwendet werden. Um die Anwendung vollständig zu lokalisieren, müssen Sie nicht nur die Ressourcen der Anwendung, sondern auch die Ressourcen, die direkt von MFC stammen zu lokalisieren. MFC enthält eine Anzahl von einer anderen Sprache Ressourcendateien automatisch, sodass ist die Sprache, die das Ziel einer der Sprachen, die bereits MFC unterstützt, nur müssen sicherstellen, dass Sie die lokalisierten Ressourcen verwenden.  
  
 Zum Zeitpunkt dieses Artikels unterstützt MFC Chinesisch, Deutsch, Spanisch, Französisch, Italienisch, Japanisch und Koreanisch. Die Dateien, die folgenden lokalisierten Versionen enthalten sind, in der MFC\INCLUDE\L.* (die "L" steht für lokalisierte) Verzeichnisse. Die deutschen Dateien sind in MFC\INCLUDE\L.DEU, z. B. ein. Ihre Anwendung diese RC-Dateien verwenden, statt die Dateien im MFC\INCLUDE hinzu, damit eine `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` an die RC-Befehlszeile (Dies ist nur ein Beispiel, müssen Sie zu ersetzen, das Gebietsschema der Wahl als auch für das Verzeichnis, in die Installation von Visual C# ++).  
  
 Die oben genannten Anweisungen funktionieren, wenn Ihre Anwendung statisch mit MFC verknüpft ist. Die meisten Anwendungen verknüpfen dynamisch (da dies die Standardeinstellung von AppWizard ist). In diesem Szenario wird nicht nur der Code dynamisch verknüpft - Ressourcen sind. Daher können Sie Ihre Ressourcen in Ihrer Anwendung lokalisieren, aber die MFC-Implementierung-Ressourcen werden noch geladen werden, aus der MFC7x.DLL (oder eine höhere Version) oder aus MFC7xLOC.DLL falls vorhanden. Sie können diese annähern, aus zwei verschiedenen Blickwinkeln dar.  
  
 Die komplexere Ansatz zum Versenden eines lokalisierten MFC7xLOC.DLLs (z. B. MFC7xDEU, Deutsch, MFC7xESP.DLL für Spanisch usw.) oder eine höhere Version ist, und installieren die entsprechenden MFC7xLOC.DLL in das Verzeichnis "System", wenn der Benutzer die Anwendung installiert. Dies kann für Entwickler und Endbenutzer sehr komplex sein und wird daher nicht empfohlen. Finden Sie unter [technischen Hinweis 56](../mfc/tn056-installation-of-localized-mfc-components.md) für Weitere Informationen zu dieser Technik und seine Fallstricke.  
  
 Die einfachste und sicherste Methode ist die lokalisierten MFC-Ressourcen in Ihrer Anwendung oder DLL selbst (oder die Satelliten-DLL, wenn Sie eine verwenden) eingeschlossen werden sollen. Dadurch werden Probleme mit MFC7xLOC.DLL ordnungsgemäß zu installieren. Voraussetzung hierfür ist, Sie führen Sie dieselben Anleitungen für die statische Groß-/Kleinschreibung, die oben genannte (Festlegen der RC-Befehlszeile ordnungsgemäß, um auf die lokalisierten Ressourcen zu verweisen), außer, dass Sie auch entfernen, müssen die `/D_AFXDLL` definieren, die von AppWizard hinzugefügt wurde. Wenn `/D_AFXDLL` wird definiert, AFXRES. H (und die anderen MFC-RC-Dateien) tatsächlich definieren alle Ressourcen (da sie von MFC-DLLs stattdessen abgerufen werden, werden).  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

