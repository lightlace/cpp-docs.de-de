---
title: Festlegen der Breite einer horizontalen Bildlaufleiste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 671da02bd1b836cd482c057c09ab31d27b42843f
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314656"
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>Festlegen der Breite einer horizontalen Bildlaufleiste

Wenn Sie ein Listenfeld mit einer horizontalen Schiebeleiste eines Dialogfelds mithilfe von MFC-Klassen hinzufügen, wird die Bildlaufleiste nicht automatisch in Ihrer Anwendung angezeigt.

### <a name="to-make-the-scroll-bar-appear"></a>Auf der Bildlaufleiste anzuzeigen

1. Legen Sie eine maximale Breite für das breiteste Element durch Aufrufen von [CListBox:: SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) in Ihrem Code.

   Ohne diesen Wert die Bildlaufleiste selbst nicht angezeigt, wenn die Elemente im Listenfeld breiter als das Feld sind.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

MFC

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)  
[Steuerelemente](../mfc/controls-mfc.md)