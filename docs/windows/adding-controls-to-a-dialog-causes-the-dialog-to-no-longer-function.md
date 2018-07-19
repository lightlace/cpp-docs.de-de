---
title: Hinzufügen von Steuerelementen zu einem Dialogfeld führt dazu, dass das Dialogfeld nicht mehr funktioniert | Microsoft Docs
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
ms.openlocfilehash: b10c24955e74d08ab570b5b694628f42bb394268
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858993"
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>Das Dialogfeld funktioniert nach dem Hinzufügen von Steuerelementen nicht mehr
Nach dem Hinzufügen einer allgemeinen Steuerelements oder eine rich-Edit-Steuerelement in einem Dialogfeld an, es nicht angezeigt, wenn Sie das Dialogfeld Testen oder das Dialogfeld selbst wird nicht angezeigt.  
  
 **Beispiel für das problem**  
  
1.  Erstellen Sie ein Win32-Projekt, und ändern die Anwendungseinstellungen, daher Sie eine Windows-Anwendung (keine Konsolen-app erstellen).  
  
2.  In [Ressourcenansicht](../windows/resource-view-window.md), einen Doppelklick auf die RC-Datei.  
  
3.  Klicken Sie unter der Dialogfeldoption Doppelklicken auf die **zu** Feld.  
  
4.  Hinzufügen einer **IP-Adressensteuerelement** auf das Dialogfeld.  
  
5.  Speichern und **alle neu erstellen**.  
  
6.  Führen Sie das Programm an.  
  
7.  Auf des Dialogfelds **Hilfe** Menü klicken Sie auf der **zu** Befehl; kein Dialogfeld angezeigt wird.  
  
 **Die Ursache**  
  
 Derzeit werden Dialog-Editor nicht automatisch hinzugefügt Code zu Ihrem Projekt beim Ziehen und Ablegen der folgenden allgemeinen Steuerelemente oder Rich--Steuerelemente in einem Dialogfeld Edit. Und Visual Studio bietet einen Fehler oder eine Warnung, wenn dieses Problem auftritt. Sie müssen den Code für das Steuerelement manuell hinzufügen.  
  
||||  
|-|-|-|  
|Schiebereglersteuerung|Strukturansicht-Steuerelements|Datums-/Zeitauswahl|  
|Drehfeld-Steuerelement|Registerkarten-Steuerelement|Monatskalender|  
|Statuskontrolle|Animation-Steuerelement|IP-Adressensteuerelement|  
|Abkürzungstaste|Rich-Edit-Steuerelement|Erweitertes Kombinationsfeld|  
|Strukturelement-Steuerelement|Rich Edit 2.0-Steuerelement|Benutzerdefiniertes Steuerelement|  
  
## <a name="the-fix-for-common-controls"></a>Fehlerbehebung für allgemeine Steuerelemente  
 Um allgemeine Steuerelemente in einem Dialogfeld verwenden zu können, müssen Sie rufen [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) oder **AFXInitCommonControls aufgerufen werden** vor dem Erstellen des Dialogfelds "".  
  
## <a name="the-fix-for-richedit-controls"></a>Fehlerbehebung für RichEdit-Steuerelemente  
 Rufen Sie **LoadLibrary** für Rich--Steuerelemente Edit. Weitere Informationen finden Sie unter [Verwenden des RichEdit 1.0-Steuerelements mit MFC](../windows/using-the-richedit-1-0-control-with-mfc.md), [über Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) in der [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)], und [Überblick über das Rich-Edit-Steuerelement](../mfc/overview-of-the-rich-edit-control.md).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Problembehandlung für den Dialog-Editor](../windows/troubleshooting-the-dialog-editor.md)   
 [Dialog-Editor](../windows/dialog-editor.md)

