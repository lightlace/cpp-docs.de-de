---
title: 'TN057: Lokalisierung von MFC-Komponenten'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.components
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
ms.openlocfilehash: 812c2d29c42b523d7b88b03741dc20f08ee70f44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428638"
---
# <a name="tn057-localization-of-mfc-components"></a>TN057: Lokalisierung von MFC-Komponenten

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt einige der Entwürfe und Verfahren, die Sie zum Lokalisieren Ihrer Komponentennamens verwenden können, wenn sie eine Anwendung oder ein OLE-Steuerelement oder eine DLL, die MFC verwendet.

## <a name="overview"></a>Übersicht

Es gibt zwei Probleme beim Auflösen eine Komponente, MFC verwendet, lokalisieren. Zunächst müssen Sie Ihre eigenen Ressourcen lokalisieren, Zeichenfolgen, Dialogfelder und andere Ressourcen, die für die Komponente spezifisch sind. Die meisten Komponenten, die mithilfe von MFC auch erstellt und verwenden eine Reihe von Ressourcen, die von MFC definiert sind. Sie müssen auch lokalisierte MFC-Standardressourcen angeben. Glücklicherweise werden mehrere Sprachen, bereits von MFC selbst bereitgestellt.

Darüber hinaus sollte die Komponente vorbereitet werden, in die zielumgebung (Europäische oder DBCS-fähigen Umgebung) ausführen. Zum größten Teil, hängt dies für Ihre Anwendung zum Behandeln von Zeichen mit festgelegtem hohem Bit richtig und Arbeiten mit Zeichenfolgen, double-Byte-Zeichen. MFC ist, in der Standardeinstellung für beide Umgebungen, aktiviert, es ist möglich, dass eine einzelne weltweite Binärdatei, die mit verschiedenen Ressourcen, die beim Setup angeschlossen auf allen Plattformen verwendet wird.

## <a name="localizing-your-components-resources"></a>Lokalisieren von Ressourcen für Ihre Komponente

Lokalisieren von Ihrer Anwendung oder DLL sollten die Anpassungen ersetzen einfach die Ressourcen mit Ressourcen, die der Zielsprache entsprechen. Für Ihre eigenen Ressourcen, ist dies relativ einfach: die Ressourcen im Ressourcen-Editor bearbeiten und erstellen Sie Ihre Anwendung. Wenn Ihr Code richtig geschrieben ist, darauf hinweisen, dass keine Zeichenfolgen oder Text, den Sie zum Lokalisieren von hartcodierten in Ihren C++-Quellcode möchten - alle Lokalisierung möglich durch das Ändern von Ressourcen. In der Tat können Sie Ihre Komponente implementieren, so, dass alle Bereitstellen einer lokalisierten Version keine sogar einen Build des ursprünglichen Codes verbunden ist. Dies ist komplexer, aber lohnt sich gut und ist der Mechanismus für MFC selbst ausgewählt. Es ist auch möglich, eine Anwendung zu lokalisieren, indem Sie die EXE- oder DLL-Datei in den Ressourcen-Editor zu laden und die Ressourcen direkt zu bearbeiten. Dies ist zwar möglich ist es erforderlich, erneute Anwendung dieser Änderungen jedes Mal, wenn Sie eine neue Version Ihrer Anwendung erstellen.

Eine Möglichkeit, dies zu vermeiden ist, um alle Ressourcen in einer separaten DLL, bezeichnet eine Satelliten-DLL zu suchen. Diese DLL-Datei wird dann zur Laufzeit dynamisch geladen und die Ressourcen aus dieser DLL statt über das Hauptmodul für den gesamten Code geladen werden. MFC unterstützt direkt diesen Ansatz. Erwägen Sie eine Anwendung namens "MyApp". EXE-DATEI; Er kann alle seine Ressourcen in eine DLL mit MYRES aufweisen. DLL. In der Anwendung `InitInstance` würden sie Folgendes ein, um die DLL zu laden und dazu führen, dass MFC zum Laden von Ressourcen von diesem Ort aus ausführen:

```cpp
CMyApp::InitInstance()
{
    // one of the first things in the init code
    HINSTANCE hInst = LoadLibrary("myres.dll");

    if (hInst != NULL)
        AfxSetResourceHandle(hInst);

    // other initialization code would follow
    // ...
}
```

Anschließend wird in MFC Ressourcen aus dieser DLL statt aus myapp.exe geladen werden. Alle Ressourcen müssen sich jedoch in die DLL vorhanden sein; MFC wird-Instanz der Anwendung auf der Suche nach einer bestimmten Ressource nicht gesucht werden. Diese Technik gilt gleichermaßen als auch für reguläre MFC-DLLs sowie von OLE-Steuerelementen. Das Setupprogramm kopiert die entsprechende Version von MYRES. Je nachdem welches Gebietsschema Resource DLL möchte der Benutzer.

Es ist relativ einfach, erstellen Sie eine Ressource nur DLL. Sie erstellen eine DLL-Projekt, fügen Sie Ihrer. RC-Datei, und fügen Sie die erforderlichen Ressourcen hinzu. Wenn Sie ein vorhandenes Projekt, das diese Technik nicht verwendet verfügen, können Sie die Ressourcen aus dem Projekt kopieren. Nach dem Hinzufügen der Ressourcendatei für das Projekt, sind Sie fast bereit, die das Projekt zu erstellen. Das einzige, was Sie tun müssen, ist der Linker die Optionen zum Festlegen **/NOENTRY**. Dies weist den Linker an, dass die DLL ohne Einstiegspunkt - aufweist, da es keinen Code enthält, verfügt er über keinen Einstiegspunkt.

> [!NOTE]
> Der Ressourcen-Editor in Visual C++ 4.0 und höher unterstützt mehrere Sprachen pro. RC-Datei. Dadurch kann es sehr einfach, Ihre Lokalisierung in einem einzelnen Projekt zu verwalten sein. Die Ressourcen für jede Sprache werden von Präprozessordirektiven, die von den Ressourcen-Editor generierten gesteuert.

## <a name="using-the-provided-mfc-localized-resources"></a>Verwenden die MFC-Bibliothek bereitgestellte lokalisierte Ressourcen

Jeder MFC-Anwendung, die Sie erstellen verwendet zwei Dinge von MFC: Code und Ressourcen. Das heißt, hat die MFC verschiedene Fehlermeldungen, integrierten Dialogfelder und andere Ressourcen, die von der MFC-Klassen verwendet werden. Um die Anwendung vollständig zu lokalisieren, müssen Sie lokalisieren, nicht nur die Ressourcen der Anwendung, sondern auch die Ressourcen, die direkt von MFC bereitgestellt werden. MFC bietet eine Reihe von anderen Sprache Ressourcendateien automatisch, damit ist die Sprache, die Sie Anzielen einer der Sprachen, die MFC bereits unterstützt, Sie lediglich sicherstellen, dass Sie die lokalisierten Ressourcen verwenden.

Während ich dies schreibe unterstützt MFC, Chinesisch, Deutsch, Spanisch, Französisch, Italienisch, Japanisch und Koreanisch. Die Dateien, die diese lokalisierten Versionen enthalten sind, in der MFC\INCLUDE\L.* ("L" steht für die lokalisierte) Verzeichnisse. Die deutschen Dateien sind im MFC\INCLUDE\L.DEU, z. B. ein. Um Ihre Anwendung diese RC-Dateien verwenden, statt die Dateien im MFC\INCLUDE verursacht, fügen einen `/IC:\PROGRAM FILES\MICROSOFT VISUAL STUDIO .NET 2003\VC7\MFC\INCLUDE\L.DEU` auf die RC-Befehlszeile (Dies ist nur ein Beispiel, müssen Sie Ihr Gebietsschema Ihrer Wahl sowie das Verzeichnis, in dem Visual C installiert, ersetzen ++).

Die obigen Anweisungen funktioniert, wenn Ihre Anwendung statisch mit MFC verknüpft ist. Die meisten Anwendungen verknüpfen dynamisch (da dies die Standardeinstellung von AppWizard ist). In diesem Szenario wird nicht nur der Code dynamisch verknüpft ist – die Ressourcen sind. Daher können Sie Ihre Ressourcen in Ihrer Anwendung lokalisieren, aber die MFC-Implementierung Ressourcen werden noch geladen werden, aus der MFC7x.DLL (oder eine höhere Version) oder aus MFC7xLOC.DLL falls vorhanden. Sie können dies aus zwei verschiedenen Blickwinkeln angehen.

Die komplexere Ansatz zum Versenden eines der lokalisierten MFC7xLOC.DLLs (z. B. MFC7xDEU, Deutsch, MFC7xESP.DLL für Spanisch usw.) oder eine höhere Version ist, und installieren die entsprechenden MFC7xLOC.DLL ins Systemverzeichnis, wenn der Benutzer die Anwendung installiert. Dies kann für Entwickler und Endbenutzer sehr komplex sein und ist daher nicht empfohlen. Finden Sie unter [technischen Hinweis 56](../mfc/tn056-installation-of-localized-mfc-components.md) für Weitere Informationen zu dieser Technik und der Einschränkungen.

Die einfachste und sicherste Methode ist, enthalten die lokalisierten Ressourcen für MFC in Ihrer Anwendung oder DLL selbst (oder die Satelliten-DLL, wenn Sie einen verwenden). Dadurch werden Probleme mit MFC7xLOC.DLL ordnungsgemäß zu installieren. Zu diesem Zweck Sie die gleichen Anweisungen für den statischen Fall oben (Festlegen der RC-Befehlszeile ordnungsgemäß, um auf die lokalisierten Ressourcen zu verweisen) angegebenen befolgen, außer, dass Sie auch entfernen, müssen die `/D_AFXDLL` definieren, die von AppWizard hinzugefügt wurde. Wenn `/D_AFXDLL` wird definiert, AFXRES. H (und die anderen MFC-RC-Dateien) ist nicht tatsächlich Ressourcen definiert (da sie von der MFC-DLLs stattdessen gezogen werden).

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
