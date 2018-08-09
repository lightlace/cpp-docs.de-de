---
title: Benutzerdefinierte Steuerelemente im Dialog-Editor | Microsoft-Dokumentation
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
ms.openlocfilehash: 0b197baa61d741452219529e44be0e9ba1a154ce
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651050"
---
# <a name="custom-controls-in-the-dialog-editor"></a>Benutzerdefinierte Steuerelemente im Dialog-Editor
Der Dialog-Editor können Sie vorhandene "Benutzerdefiniert" oder "User"-Steuerelemente in eine Dialogfeldvorlage.  
  
> [!NOTE]
>  Benutzerdefinierte Steuerelemente in diesem Zusammenhang sind nicht zu verwechseln mit ActiveX-Steuerelementen. ActiveX-Steuerelemente wurden benutzerdefinierte OLE-Steuerelemente bezeichnet. Verwechseln Sie nicht auch diese Steuerelemente mit den ownerdrawn-Steuerelementen in Windows.  
  
 Diese Funktion dient als die vom Windows-Steuerelemente verwenden zu können. Zur Laufzeit für das Steuerelement eine Fensterklasse (nicht die gleiche als C++-Klasse) zugeordnet ist. Eine allgemeinere Möglichkeit zum Ausführen der gleichen Aufgabe besteht darin Kontrolle, z. B. ein statisches Steuerelement in einem Dialogfeld zu installieren. Klicken Sie dann zur Laufzeit in die [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) funktionieren, entfernen Sie das Steuerelement aus, und durch Ihr eigenes benutzerdefiniertes Steuerelement ersetzen.  
  
 Dies ist eine alte Technik. Noch heute in den meisten Fällen sollten Sie ein ActiveX-Steuerelement oder eine Unterklasse eines allgemeinen Steuerelements von Windows zu schreiben.  
  
 Für benutzerdefinierte Steuerelemente sind Sie auf:  
  
-   Festlegen des Speicherorts im Dialogfeld an.  
  
-   Eingeben einer Beschriftung.  
  
-   Identifizieren den Namen der Windows-Klasse des Steuerelements (Ihr Anwendungscode muss das Steuerelement mit diesem Namen registrieren).  
  
-   Geben einen 32-Bit-Hexadezimalwert, das Format des Steuerelements legt diese fest.  
  
-   Wenn den erweiterten Stil.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)