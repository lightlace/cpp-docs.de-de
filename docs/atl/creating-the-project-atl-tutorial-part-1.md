---
title: Erstellen des Projekts (ATL-Lernprogramm, Teil 1) | Microsoft-Dokumentation
ms.custom: get-started-article
ms.date: 09/26/2018
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd53bc778b3229522d34993c72833500732323b3
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821100"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Erstellen des Projekts (ATL-Lernprogramm, Teil 1)

Dieses Tutorial führt Sie schrittweise durch ein nicht attributierte ATL-Projekt, das ein ActiveX-Objekt erstellt, die ein Polygon anzeigt. Das Objekt enthält die Optionen für die es den Benutzer ermöglicht, so ändern Sie die Anzahl der Seiten, aus denen die Polygon- und Code auf die Anzeige zu aktualisieren.

> [!NOTE]
> ATL und MFC sind in den Express-Editionen von Visual Studio in der Regel nicht unterstützt.

> [!NOTE]
> In diesem Tutorial wird den gleiche Quellcode als Beispiel für Polygon erstellt. Wenn Sie vermeiden, den Quellcode manuell eingeben möchten, können Sie herunterladen, aus der [Polygon-Beispiel](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon). Sie können dann auf den Quellcode des Polygons verweisen, wie Sie das Lernprogramm zu absolvieren, oder verwenden, um Fehler in Ihrem eigenen Projekt zu prüfen.
> Klicken Sie zum Kompilieren "stdafx.h" zu öffnen, und ersetzen:
> ```
> #ifndef WINVER  
> #define WINVER 0x0400   
> #endif
> ```
> durch
> ```
> #ifndef WINVER  
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
> Der Compiler wird immer noch über einen Fehler `regsvr32` nicht ordnungsgemäß beendet, aber Sie sollten immer noch die DLL des Steuerelements erstellt und für die Verwendung verfügbar.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>Zum Erstellen des anfänglichen ATL-Projekts mit ATL-Projektassistenten

1. Klicken Sie in der Visual Studio-Entwicklungsumgebung auf **neu** auf die **Datei** , und klicken Sie dann auf **Projekt**.

1. Öffnen der **Visual C++** Registerkarte, und wählen Sie **MFC/ATL**. Wählen Sie **ATL-Projekt**.

1. Typ *Polygon* als Projektnamen ein.

    Der Speicherort für den Quellcode in der Regel standardmäßig \Users\\\<Benutzername > \source\repos und einen neuen Ordner wird automatisch erstellt.

1. Klicken Sie auf **OK** und **ATL-Projekt** -Assistent wird geöffnet.

1. Klicken Sie auf **Anwendungseinstellungen** um die verfügbaren Optionen anzuzeigen.

1. Lassen Sie, wie Sie ein Steuerelement erstellen und ein Steuerelement muss in-Process-Server sein, die **Anwendungstyp** als DLL.

1. Behalten Sie die anderen Optionen die Standardwerte bei, und klicken Sie auf **OK**.

Die **ATL-Projektassistenten** erstellt das Projekt, indem Sie mehrere Dateien zu generieren. Sie können diese Dateien in anzeigen **Projektmappen-Explorer** durch Erweitern der `Polygon` Objekt. Die Dateien sind unten aufgeführt.

|Datei|Beschreibung|
|----------|-----------------|
|Polygon.cpp hinzu|Enthält die Implementierung der `DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`, und `DllUnregisterServer`. Außerdem enthält der objektzuordnung, das eine Liste der ATL-Objekte in Ihrem Projekt ist. Dies ist zunächst leer.|
|Polygon.def|Diese DEF-Datei enthält den Linker mit Informationen über die Exporte, die die DLL erforderlich sind.|
|Polygon.idl|Die IDL-Datei, die die Schnittstellen, die spezifisch für Ihre Objekte beschreibt.|
|Polygon.RGS|Dieses Registrierungsskript enthält Informationen zum Registrieren Ihres Programms-DLL.|
|Polygon.rc|Die Ressourcendatei, die zunächst die Informationen zur Version und eine Zeichenfolge, enthält den Namen des Projekts enthält.|
|Resource.h|Die Headerdatei für die Ressourcendatei|
|Polygonps.def|Moduldefinitionsdatei enthält den Linker mit Informationen über die Exporte benötigt, durch den Proxy und Stub-Code, die Aufrufe über Apartments hinweg zu unterstützen.|
|stdafx.cpp|Die Datei, die `#include` die ATL-Implementierungsdateien.|
|stdafx.h|Die Datei, die `#include` ATL-Headerdateien.|

1. In **Projektmappen-Explorer**, mit der rechten Maustaste die `Polygon` Projekt.

1. Klicken Sie im Kontextmenü auf **Eigenschaften**.

1. Klicken Sie auf **Linker**. Ändern der **pro UserRedirection** option **Ja**.

1. Klicken Sie auf **OK**.

Im nächsten Schritt fügen Sie ein Steuerelement zu Ihrem Projekt hinzu.

[Schritt 2](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
