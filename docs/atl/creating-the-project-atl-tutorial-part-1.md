---
title: Erstellen des Projekts (ATL-Lernprogramm, Teil 1) | Microsoft-Dokumentation
ms.custom: get-started-article
ms.date: 11/04/2016
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
ms.openlocfilehash: 54b45ff8c7af8c8aaf7232cefa2bb4f002fc37be
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755617"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Erstellen des Projekts (ATL-Lernprogramm, Teil 1)

Dieses Tutorial führt Sie schrittweise durch ein nicht attributierte ATL-Projekt, das ein ActiveX-Objekt erstellt, die ein Polygon anzeigt. Das Objekt enthält die Optionen für die es den Benutzer ermöglicht, so ändern Sie die Anzahl der Seiten, aus denen die Polygon- und Code auf die Anzeige zu aktualisieren.

> [!NOTE]
>  ATL und MFC sind in den Express-Editionen von Visual Studio in der Regel nicht unterstützt.

> [!NOTE]
>  In diesem Tutorial wird den gleiche Quellcode als Beispiel für Polygon erstellt. Wenn Sie vermeiden, den Quellcode manuell eingeben möchten, können Sie herunterladen, aus der [Polygon-Beispiel](../visual-cpp-samples.md). Sie können dann auf den Quellcode des Polygons verweisen, wie Sie das Lernprogramm zu absolvieren, oder verwenden, um Fehler in Ihrem eigenen Projekt zu prüfen.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>Zum Erstellen des anfänglichen ATL-Projekts mit ATL-Projektassistenten

1. Klicken Sie in der Visual Studio-Entwicklungsumgebung auf **neu** auf die **Datei** , und klicken Sie dann auf **Projekt**.

2. Klicken Sie auf die **Visual C++-Projekte** Ordner, und wählen **ATL-Projekt**.

3. Typ *Polygon* als Projektnamen ein.

     Der Speicherort für den Quellcode in der Regel standardmäßig Eigene Dateien\Visual Studio-Projekte, und ein neuer Ordner wird automatisch erstellt.

4. Klicken Sie auf **OK** und der ATL-Projekt-Assistent wird geöffnet.

5. Klicken Sie auf **Anwendungseinstellungen** um die verfügbaren Optionen anzuzeigen.

6. Lassen Sie, wie Sie ein Steuerelement erstellen und ein Steuerelement muss in-Process-Server sein, die **Anwendungstyp** als DLL.

7. Behalten Sie die anderen Optionen die Standardwerte bei, und klicken Sie auf **Fertig stellen**.

ATL-Projektassistenten wird das Projekt erstellen, indem Sie mehrere Dateien zu generieren. Sie können diese Dateien im Projektmappen-Explorer anzeigen, indem Sie das Objekt Polygon erweitern. Die Dateien sind unten aufgeführt.

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

1. Klicken Sie im Projektmappen-Explorer mit der Maustaste der `Polygon` Projekt.

2. Klicken Sie im Kontextmenü auf **Eigenschaften**.

3. Klicken Sie auf **Linker**. Ändern der **pro UserRedirection** option **Ja**.

4. Klicken Sie auf **OK**.

Im nächsten Schritt fügen Sie ein Steuerelement zu Ihrem Projekt hinzu.

[Schritt 2](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>Siehe auch

[Tutorial](../atl/active-template-library-atl-tutorial.md)
