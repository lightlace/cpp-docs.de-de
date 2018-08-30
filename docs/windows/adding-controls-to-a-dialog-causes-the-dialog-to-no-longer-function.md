---
title: Hinzufügen von Steuerelementen zu einem Dialogfeld bewirkt, dass das Dialogfeld nicht mehr funktioniert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], troubleshooting
- common controls, troubleshooting
- troubleshooting controls
- dialog boxes, troubleshooting
- dialog box controls, troubleshooting
- InitCommonControls
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d27c12b491fc5f05da58a84703ea13e84e9e9c6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215369"
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>Das Dialogfeld funktioniert nach dem Hinzufügen von Steuerelementen nicht mehr

Nach dem Hinzufügen einer allgemeinen Steuerelements oder rich-Edit-Steuerelement in einem Dialogfeld an, es nicht angezeigt, wenn Sie Sie das Dialogfeld Testen oder das Dialogfeld nicht angezeigt.

### <a name="example-of-the-problem"></a>Beispiel für das problem

1. Erstellen Sie eine Win32-Projekts, das die Anwendungseinstellungen ändern, damit Sie eine Windows-Anwendung (keine Konsolen-app erstellen).

2. In [Ressourcenansicht](../windows/resource-view-window.md), einen Doppelklick auf die RC-Datei.

3. Wählen Sie unter der Dialogfeldoption Doppelklicken klicken Sie auf die **zu** Feld.

4. Hinzufügen einer **IP-Adressensteuerelement** auf das Dialogfeld.

5. Speichern und **alles neu erstellen**.

6. Führen Sie das Programm an.

7. In des Dialogfelds **helfen** im Menü klicken Sie auf die **zu** Befehl, kein Dialogfeld angezeigt wird.

### <a name="the-cause"></a>Die Ursache

Derzeit wird der Dialog-Editor nicht automatisch hinzugefügt Code zu Ihrem Projekt beim Drag & drop die folgenden allgemeinen Steuerelemente oder Rich--Steuerelemente in einem Dialogfeld Edit. Auch Visual Studio bietet Fehler oder Warnung, wenn dieses Problem auftritt. Sie müssen den Code für das Steuerelement manuell hinzufügen.

||||
|-|-|-|
|Schiebereglersteuerung|Strukturansicht-Steuerelement|Datums-/Zeitauswahl|
|Drehfeld-Steuerelement|Registerkarten-Steuerelement|Monatskalender|
|Statuskontrolle|Animation-Steuerelement|IP-Adressensteuerelement|
|Abkürzungstaste|Rich Edit-Steuerelements|Erweitertes Kombinationsfeld|
|Listensteuerelement|Rich Edit 2.0-Steuerelements|Benutzerdefiniertes Steuerelement|

## <a name="the-fix-for-common-controls"></a>Das Update für allgemeine Steuerelemente

Um allgemeine Steuerelemente in einem Dialogfeld verwenden zu können, müssen Sie rufen [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) oder `AFXInitCommonControls` vor der Erstellung des Dialogfelds.

## <a name="the-fix-for-richedit-controls"></a>Die Fehlerbehebung für RichEdit-Steuerelemente

Rufen Sie `LoadLibrary` für Rich--Steuerelemente Edit. Weitere Informationen finden Sie unter [Verwenden des RichEdit 1.0-Steuerelements mit MFC](../windows/using-the-richedit-1-0-control-with-mfc.md), [über Rich-Edit-Steuerelemente](/windows/desktop/Controls/about-rich-edit-controls) im Windows SDK und [Überblick über das RichEdit-Steuerelement](../mfc/overview-of-the-rich-edit-control.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Problembehandlung beim Dialog-Editor](../windows/troubleshooting-the-dialog-editor.md)  
[Dialog-Editor](../windows/dialog-editor.md)