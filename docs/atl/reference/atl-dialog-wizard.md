---
title: ATL-Dialogfeld-Assistenten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 43540b1b86dbbf1777e7d5a7f6d8dec5dc618334
ms.lasthandoff: 02/24/2017

---
# <a name="atl-dialog-wizard"></a>ATL-Dialogfeld-Assistent
Dieser Assistent fügt dem Projekt eine ATL-Dialogfeldobjekt abgeleitet [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Ein Dialogfeld abgeleitet `CAxDialogImpl` können ActiveX-Steuerelemente hosten.  
  
 Der Assistent erstellt eine Dialogressource mit **OK** und **Abbrechen** Schaltflächen. Können die Dialogressource bearbeiten und Hinzufügen von ActiveX-Steuerelemente verwenden die [Dialog-Editor](../../windows/dialog-editor.md) in der Ressourcenansicht.  
  
 Der Assistent fügt die Headerdatei ein [meldungszuordnung](../../atl/message-maps-atl.md) und Deklarationen für die Behandlung von Standard auf Ereignisse. Finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) Weitere Informationen über ATL-Dialogfelder.  
  
 **Kurzname**  
 Legt den abgekürzten Namen für das ATL-Dialogfeldobjekt fest. Der hier angegebene Name bestimmt den Klassennamen und die Dateinamen (.cpp und .h), wenn Sie diese Felder nicht einzeln ändern.  
  
 `Class`  
 Legt den Namen der Klasse erstellt werden. Dieser Name basiert auf den Namen, den Sie in **Kurznamen**, 'C', das Standard-Präfix für einen Klassennamen vorangestellt.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf den Namen, den Sie in **Kurznamen**. Klicken Sie auf die Schaltfläche, um den Dateinamen am Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei anfügen. Wenn Sie eine vorhandene Datei auswählen, der Assistent wird gespeichert, am ausgewählten Speicherort bis auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei, auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für die neue Klasse des Objekts. Dieser Name basiert standardmäßig auf den Namen, den Sie in **Kurznamen**. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen am Speicherort Ihrer Wahl zu speichern. Die Datei wird nicht am ausgewählten Speicherort gespeichert, bis Sie auf **Fertig stellen** im Assistenten.  
  
 Der Assistent überschrieben eine Datei nicht. Wenn Sie den Namen einer vorhandenen Datei, auswählen, wenn Sie auf **Fertig stellen**, die vom Assistenten aufgefordert, anzugeben, ob die Implementierung der Klasse an den Inhalt der Datei angefügt werden sollen. Klicken Sie auf **Ja** anzufügenden Datei ein, klicken Sie auf **keine** zum Assistenten zurückzukehren und einen anderen Dateinamen angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Dialogfeld](../../atl/reference/adding-an-atl-dialog-box.md)


