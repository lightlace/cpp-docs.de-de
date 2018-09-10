---
title: Neue Symbolleiste Ressource (Dialogfeld) (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.newtoolbarresource
dev_langs:
- C++
helpviewer_keywords:
- New Toolbar Resource dialog box [C++]
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ca09463a2934db0097c09d6a4f928f108fd0760
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316301"
---
# <a name="new-toolbar-resource-dialog-box-c"></a>Neue Symbolleiste Ressource (Dialogfeld) (C++)

Die **neue Symbolleistenressource** Dialogfeld können Sie angeben, die Breite und Höhe der Schaltflächen einer Symbolleistenressource in einem C++-Projekt hinzufügen. Der Standardwert ist 16 × 15 Pixel.

Eine Bitmap, die zum Erstellen einer Symbolleiste verwendet wird, hat eine maximale Breite von 2048. Wenn Sie festlegen, also die **Schaltflächenbreite** auf 512, können Sie nur vier Schaltflächen haben. Wenn Sie die Breite auf 513 festlegen, können Sie nur drei Schaltflächen verwenden.

### <a name="button-width"></a>Schaltflächenbreite

Dient zur Eingabe von der Breite für die Symbolleisten-Schaltflächen, die Sie aus einer Bitmap-Ressource in einer Symbolleistenressource konvertieren. Die Bilder werden zugeschnitten, um die Breite und Höhe angegeben, und die Farben werden angepasst, um die Farben der Standardsymbolleiste (16 Farben) zu verwenden.

### <a name="button-height"></a>Schaltflächenhöhe

Dient zur Eingabe von der Höhe für die Symbolleisten-Schaltflächen, die Sie aus einer Bitmap-Ressource in einer Symbolleistenressource konvertieren. Die Bilder werden zugeschnitten, um die Breite und Höhe angegeben, und die Farben werden angepasst, um die Farben der Standardsymbolleiste (16 Farben) zu verwenden.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Eigenschaften von Symbolleisten-Schaltflächen](../windows/toolbar-button-properties.md)  
[Konvertieren von Bitmaps in Symbolleisten](../windows/converting-bitmaps-to-toolbars.md)  
[Symbolleisten-Editor](../windows/toolbar-editor.md)