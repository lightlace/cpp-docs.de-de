---
title: 'TN020: ID Naming- und Nummerierungskonventionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.id
dev_langs:
- C++
helpviewer_keywords:
- TN020
- resource identifiers, naming and numbering
- resource identifiers
ms.assetid: aecbd2cf-68b3-47f6-ae21-b1f507917245
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b66fa88a98f800c77e2b6b0a731bbd40df9eb9d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054630"
---
# <a name="tn020-id-naming-and-numbering-conventions"></a>TN020: ID-Benennungs- und Nummerierungskonventionen

In diesem Hinweis werden die Benennungs- und -Nummerierungskonventionen für IDs erläutert, die in MFC 2.0 für Ressourcen, Befehle, Zeichenfolgen, Steuerelemente und untergeordnete Fenster verwendet werden.

Die MFC-Benennungs- und -Nummerierungskonventionen für IDs müssen folgende Anforderungen erfüllen:

- Bereitstellen eines konsistenten ID-Benennungsstandards, der in den MFC-Bibliotheken und MFC-Anwendungen verwendet wird, die vom Visual C++-Ressourcen-Editor unterstützt werden. Damit kann der Programmierer den Typ und den Ursprung einer Ressource einfacher anhand seiner ID interpretieren.

- Hervorheben der engen 1:1-Beziehung zwischen bestimmten Typen von IDs.

- Gewährleisten von Konformität mit bereits weit verbreiteten Standards für die Benennung von IDs in Windows.

- Partitionieren des ID-Nummerierungsbereichs. ID-Nummern können vom Programmierer sowie von in MFC, Windows und Visual C++ bearbeiteten Ressourcen zugewiesen werden. Mit der entsprechenden Partitionierung kann die Duplizierungen von ID-Nummern vermieden werden.

## <a name="the-id-prefix-naming-convention"></a>Die ID-Präfix-Namenskonvention

Einige ID-Typen können in einer Anwendung auftreten. Die MFC-Benennungskonvention für ID definiert unterschiedliche Präfixe für unterschiedliche Ressourcentypen.

MFC verwendet das Präfix "IDR_", um eine Ressourcen-ID anzugeben, die für mehrere Ressourcentypen gilt. So verwendet MFC z. B. in einem bestimmten Rahmenfenster dasselbe "IDR_"-Präfix, um eine Menü-, Zugriffstasten-, Zeichenfolgen- und Symbolressource anzugeben. In der folgenden Tabelle werden die verschiedenen Präfixe und ihre Verwendung aufgeführt:

|Präfix|Mit|
|------------|---------|
|IDR_|Für mehrere Ressourcentypen (wird hauptsächlich für Menüs, Zugriffstasten und Menübänder verwendet).|
|IDD_|Für Ressourcen der Dialogfeldvorlage (z. B. IDD_DIALOG1).|
|IDC_|Für Cursorressourcen.|
|IDI_|Für Symbolressourcen.|
|IDB_|Für Bitmapressourcen.|
|IDS_|Für Zeichenfolgenressourcen.|

Innerhalb einer DIALOG-Ressource folgt MFC diesen Konventionen:

|Präfix oder Bezeichnung|Mit|
|---------------------|---------|
|IDOK, IDCANCEL|Für Standardschaltflächen-IDs.|
|IDC_|Für andere Dialogfeld-Steuerelemente.|

Das Präfix "IDC_" wird auch für Cursor verwendet. Dieser Namenskonflikt ist normalerweise kein Problem, da eine typische Anwendung über wenige Cursor und viele Dialogfeld-Steuerelemente verfügt.

Innerhalb einer Menüressource folgt MFC diesen Konventionen:

|Präfix|Mit|
|------------|---------|
|IDM_|Für Menüelemente, in denen nicht die MFC-Befehlsarchitektur verwendet wird.|
|ID_|Für Menübefehle, in denen MFC-Befehlsarchitektur verwendet wird.|

Befehle, die die MFC-befehlsarchitektur folgen müssen ein ON_COMMAND-Befehlshandler und haben einen ON_UPDATE_COMMAND_UI-Handler. Wenn diese Befehlshandler der MFC-Befehlsarchitektur folgen, funktionieren sie unabhängig davon ordnungsgemäß, ob sie an einen Menübefehl, an eine Symbolleisten-Schaltfläche oder an eine Dialogleisten-Schaltfläche gebunden sind. Das gleiche "ID_"-Präfix wird auch für eine Zeichenfolge in einer Menüeingabeaufforderung verwendet, die auf der Statusleiste des Programms angezeigt wird. Die meisten Menüelemente in der Anwendung sollten den MFC-Befehlskonventionen folgen. Alle der standard-Befehls-IDs (z. B. ID_FILE_NEW) entsprechen dieser Konvention.

MFC verwendet auch "IDP_" als eine spezielle Form von Zeichenfolgen (anstelle von "IDS_"). Zeichenfolgen mit dem Präfix "IDP_" sind Eingabeaufforderungen, d. h. Zeichenfolgen, die in Meldungsfeldern verwendet werden. "IDP_"-Zeichenfolgen können "%1" "und "%2" als Platzhalter für Zeichenfolgen enthalten, die vom Programm bestimmt werden. "IDP_"-Zeichenfolgen sind in der Regel Hilfethemen zugeordnet, während "IDS_"-Zeichenfolgen keine Hilfethemen zugeordnet sind. "IDP_"-Zeichenfolgen werden immer lokalisiert, und "IDS_"-Zeichenfolgen können nicht lokalisiert werden.

Die MFC-Bibliothek verwendet auch das Präfix "IDW_" als eine spezielle Form von Steuerelement-IDs (anstelle von "IDC_"). Diese IDs werden durch die .NET-Frameworkklassen untergeordneten Fenstern als Ansichten und Aufteilung zugewiesen. IDs für MFC-Implementierungen wird "AFX_" vorangestellt.

## <a name="the-id-numbering-convention"></a>Die ID-Nummerierungskonvention

In der folgenden Tabelle werden die gültigen Bereiche für die IDs der bestimmten Typen aufgeführt. Einige der Grenzen sind technische Implementierungsgrenzen und andere sind Konventionen, die entwickelt wurden, um zu verhindern, dass Konflikte zwischen den IDs und den von Windows vordefinierten IDs oder MFC-Standardimplementierungen auftreten.

Es wird dringend empfohlen, dass Sie alle IDs innerhalb der empfohlenen Bereiche definieren. Die Untergrenze dieser Bereiche ist 1, da 0 nicht verwendet wird. Es wird empfohlen, die allgemeine Konvention einzuhalten, 100 oder 101 als erste ID zu verwenden.

|Präfix|Ressourcentyp|Gültiger Bereich|
|------------|-------------------|-----------------|
|IDR_|mehrere|1 bis 0x6FFF|
|IDD_|Dialogfeldvorlagen|1 bis 0x6FFF|
|IDC_,IDI_,IDB_|Cursor, Symbole, Bitmaps|1 bis 0x6FFF|
|IDS_, IDP_|Allgemeine Zeichenfolgen|1 bis 0x7FFF|
|ID_|Befehle|0x8000 bis 0xDFFF|
|IDC_|Steuerelemente|8 bis 0xDFFF|

Gründe für diese Begrenzungen:

- Standardmäßig wird der ID-Wert 0 nicht verwendet.

- Durch Einschränkungen der Windows-Implementierung werden echte Ressourcen-IDs auf einen Wert kleiner oder gleich 0x7FFF eingeschränkt.

- Das interne MFC-Framework reserviert diese Bereiche:

   - 0x7000 bis 0x7FFF (siehe afxres.h)

   - 0xE000 bis 0xEFFF (siehe afxres.h)

   - 16000 bis 18000 (siehe afxribbonres.h)

   Diese Bereiche ändern sich möglicherweise in zukünftigen MFC-Implementierungen.

- Einige Windows-Systembefehle verwenden den Bereich von 0xF000 bis 0xFFFF.

- Steuerelemente-IDs von 1 bis 7 sind für Standardsteuerelemente wie IDOK und IDCANCEL reserviert.

- Der Bereich von 0x8000 bis 0xFFFF für Zeichenfolgen ist für Befehle in Menüeingabeaufforderungen reserviert.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

