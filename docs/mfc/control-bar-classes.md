---
title: Klassen für Steuerleisten
ms.date: 11/04/2016
f1_keywords:
- vc.classes.control
helpviewer_keywords:
- control bars [MFC], classes
ms.assetid: 11009103-cad8-4309-85ce-3d2e858e1818
ms.openlocfilehash: 3426d84eab888a6fe78b663945776fff2fe708dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301954"
---
# <a name="control-bar-classes"></a>Klassen für Steuerleisten

Schiebeleisten-Steuerelemente werden an ein Rahmenfenster angefügt. Sie enthalten Schaltflächen, Statusbereiche oder einer Dialogfeldvorlage. Nicht typisierte Steuerleisten, Toolpaletten, so genannte werden implementiert, indem Sie zum Anfügen einer [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md) Objekt.

## <a name="framework-control-bars"></a>Framework-Steuerleisten

Diese Schiebeleisten-Steuerelemente sind ein wesentlicher Bestandteil der MFC-Framework. Sie sind einfacher zu verwenden und leistungsfähiger, als die Windows Balken steuern, da sie in das Framework integriert sind. Die meisten MFC-Anwendungen verwenden den Windows-Steuerleisten, anstatt diese Schiebeleisten-Steuerelemente.

[CControlBar](../mfc/reference/ccontrolbar-class.md)<br/>
Die Basisklasse für MFC-Steuerelementleisten in diesem Abschnitt aufgeführt. Eine Steuerleiste ist ein Fenster, das den Rand eines Rahmenfensters ausgerichtet. Die Steuerleiste enthält entweder `HWND`-basierte untergeordnete Steuerelemente oder Steuerelemente nicht auf der Grundlage einer `HWND`, z. B. Schaltflächen der Symbolleiste.

[CDialogBar](../mfc/reference/cdialogbar-class.md)<br/>
Eine Steuerleiste, die auf eine Dialogfeldvorlage basieren.

[CReBar](../mfc/reference/crebar-class.md)<br/>
Unterstützt eine Symbolleiste, die zusätzliche untergeordnete Fenster in Form von Steuerelementen enthalten kann.

[CToolBar](../mfc/reference/ctoolbar-class.md)<br/>
Symbolleisten-Steuerelement Windows, die Bitmap-Befehlsschaltflächen, nicht enthalten basierend auf einer `HWND`. Die meisten MFC-Anwendungen verwenden Sie diese Klasse statt `CToolBarCtrl`.

[CStatusBar](../mfc/reference/cstatusbar-class.md)<br/>
Die Basisklasse für die Statusleiste Steuerelement Windows. Die meisten MFC-Anwendungen verwenden Sie diese Klasse statt `CStatusBarCtrl`.

## <a name="windows-control-bars"></a>Windows-Steuerleisten

Diese Schiebeleisten-Steuerelemente sind einfache Wrapper für die entsprechenden Windows-Steuerelemente. Da sie nicht mit dem Framework integriert sind, sind sie schwieriger zu verwenden als die oben aufgeführten Steuerleisten. Die meisten MFC-Anwendungen verwenden die zuvor aufgeführten Steuerleisten.

[CRebarCtrl](../mfc/reference/crebarctrl-class.md)<br/>
Implementiert die interne Kontrolle über die `CRebar` Objekt.

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)<br/>
Ein horizontaler Fenster unterteilt in der Regel, die Bereiche, in denen eine Anwendung Statusinformationen anzeigen kann.

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)<br/>
Stellt die Funktionalität des allgemeinen Windows-Symbolleisten-Steuerelements bereit.

## <a name="related-classes"></a>Verwandte Klassen

[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)<br/>
Ein kleines Popupfenster, in dem eine einzelne Textzeile, beschreibt den Zweck eines Tools in einer Anwendung angezeigt.

[CDockState](../mfc/reference/cdockstate-class.md)<br/>
Verarbeitet die dauerhafte Speicherung von Zustandsdaten für Schiebeleisten-Steuerelemente andocken.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
