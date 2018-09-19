---
title: Einfügen eines Abstands zwischen den Schaltflächen einer Symbolleiste (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
ms.assetid: 4925ea6b-5d3a-4949-a920-bf371a37e529
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 09086ea214bcf2abd9708f8abcee4f9f5f376994
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313415"
---
# <a name="inserting-a-space-between-buttons-on-a-toolbar-c"></a>Einfügen eines Abstands zwischen den Schaltflächen einer Symbolleiste (C++)

Im Allgemeinen um ein Leerzeichen zwischen den Schaltflächen einzufügen, ziehen Sie einfach diese von anderen auf der Symbolleiste. Um Speicherplatz zu entfernen, ziehen Sie sie in Richtung gegenseitig aus.

### <a name="to-insert-a-space-before-a-button-that-is-not-followed-by-a-space"></a>Ein Leerzeichen vor eine Schaltfläche eingefügt, die nicht durch ein Leerzeichen folgt

1. Ziehen Sie die Schaltfläche rechts oder nach unten Sie, bis sie die Schaltfläche "Weiter" während des laufenden Vorgangs zu überlappt.

### <a name="to-insert-a-space-before-a-button-which-is-followed-by-a-space-and-to-retain-that-trailing-space"></a>Ein Leerzeichen vor eine Schaltfläche eingefügt, von einem Leerzeichen gefolgt, und beibehalten, nachfolgende Leerzeichen

1. Ziehen Sie die Schaltfläche aus, bis am rechten oder unteren Rand die Schaltfläche "Weiter Schaltflächenrand", oder geringfügig überlappt.

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-close-up-that-following-space"></a>Fügen Sie ein Leerzeichen vor eine Schaltfläche, die durch ein Leerzeichen folgt, und schließen diese folgenden Speicherplatz

1. Ziehen Sie die Schaltfläche rechts oder nach unten Sie, bis sie die Schaltfläche "Weiter" während des laufenden Vorgangs zu überlappt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Erstellen, Verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../windows/creating-moving-and-editing-toolbar-buttons.md)  
[Symbolleisten-Editor](../windows/toolbar-editor.md)