---
title: Umschalten zwischen Dialogfeld-Steuerelemente und Code | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog editor, accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog editor, switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9aa603afdd6392f9dbe6082a76c1ae157bd008af
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610855"
---
# <a name="switching-between-dialog-box-controls-and-code"></a>Umschalten zwischen Dialogfeld-Steuerelementen und Code

In MFC-Anwendungen Doppelklicken Sie auf der Dialogfeld-Steuerelemente an ihrem Ereignishandlercode zu springen oder schnell Stub Handlerfunktionen erstellen.

Ein Steuerelement ausgewählt ist, und klicken Sie auf die **Steuerelementereignisse** Schaltfläche oder die **Nachrichten** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) eine vollständige Liste der Windows-Nachrichten und Ereignisse anzeigen für das ausgewählte Element verfügbar. Wählen Sie aus der Liste zum Erstellen oder Bearbeiten von Handlerfunktionen.

### <a name="to-jump-to-code-from-the-dialog-editor"></a>Um Code aus dem Dialog-Editor zu wechseln.

1. Doppelklicken Sie auf ein Steuerelement im Dialogfeld, um die Deklaration für die zuletzt implementierter Meldung, die Funktion zur Behandlung zu wechseln. (Für Dialogfeldklassen mit ATL-basiertes ruft Sie immer die Konstruktordefinition.)

### <a name="to-view-events-for-a-control"></a>So zeigen Sie Ereignisse für ein Steuerelement

1. Ein Steuerelement ausgewählt ist, und klicken Sie auf die **Steuerelementereignisse** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

   > [!NOTE]
   > Klicken auf die **Steuerelementereignisse** Schaltfläche, wenn die *Dialogfeld* verfügt über eine Liste aller Steuerelemente den Fokus verfügbar macht, in das Dialogfeld, das Sie dann so bearbeiten Sie die Ereignisse für die einzelnen Steuerelemente erweitern können.

   Wenn ein einzelnes Steuerelement den Fokus in das Dialogfeld besitzt, können Sie Maustaste und wählen **Ereignishandler hinzufügen** aus dem Kontextmenü. Dadurch können Sie die Klasse an, die der Handler hinzugefügt wird. Weitere Informationen finden Sie unter [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md).

### <a name="to-view-messages-for-a-dialog-box"></a>Um Nachrichten für ein Dialogfeld anzuzeigen.

1. Aktivieren Sie das Dialogfeld, und klicken Sie auf die **Nachrichten** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Dialog-Editor](../windows/dialog-editor.md)