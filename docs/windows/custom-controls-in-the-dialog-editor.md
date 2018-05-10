---
title: Benutzerdefinierte Steuerelemente im Dialog-Editor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- Custom Control
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], templates
- custom controls [Visual Studio], dialog boxes
- custom controls [Visual Studio]
- dialog box controls, custom (user) controls
- Dialog editor, custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2c2bca249958e4d25ab5377540525da34802ac04
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="custom-controls-in-the-dialog-editor"></a>Benutzerdefinierte Steuerelemente im Dialog-Editor
Dialog-Editor können Sie vorhandene verwenden "custom" oder "User"-Steuerelemente in einer Dialogfeldvorlage.  
  
> [!NOTE]
>  Benutzerdefinierte Steuerelemente in diesem Sinn dürfen nicht mit ActiveX-Steuerelementen verwechselt werden. ActiveX-Steuerelemente wurden benutzerdefinierte OLE-Steuerelemente bezeichnet. Verwechseln Sie nicht auch diese Steuerelemente mit den ownerdrawn-Steuerelementen in Windows.  
  
 Diese Funktion dient als die vom Windows-Steuerelemente verwenden können. Zur Laufzeit ist eine Fensterklasse (nicht identisch mit einer C++-Klasse) zugeordnet das Steuerelement. Einem häufiger für die gleiche Aufgabe besteht darin, jedes Steuerelement, z. B. ein statisches Steuerelement in einem Dialogfeld installieren. Klicken Sie dann zur Laufzeit, in der [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) -Funktion, das entsprechende Steuerelement entfernen und durch Ihr eigenes benutzerdefiniertes Steuerelement ersetzen.  
  
 Dies ist eine alte Technik. Heute sind in den meisten Fällen empfohlen, ein ActiveX-Steuerelement oder eine Unterklasse eines allgemeinen Windows-Steuerelements zu schreiben.  
  
 Für diese benutzerdefinierte Steuerelemente werden können nur:  
  
-   Festlegen des Speicherorts im Dialogfeld an.  
  
-   Eingeben einer Beschriftung.  
  
-   Identifizieren den Namen des Windows-Klasse des Steuerelements (der Anwendungscode muss das Steuerelement mit diesem Namen registriert).  
  
-   Geben Sie einen 32-Bit-Hexadezimalwert, das Format des Steuerelements festlegt.  
  
-   Festlegen der erweiterten Stils.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

