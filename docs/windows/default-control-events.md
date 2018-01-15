---
title: Standard-Steuerelementereignisse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Dialog editor, default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls, events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83c7b6e4d019b895973345805027d428d7af766d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="default-control-events"></a>Standardereignisse für Steuerelemente
Die folgenden Namen von Steuerelementen haben die zugehörigen Standardereignissen:  
  
|Steuerelementname|Standardereignis|  
|------------------|-------------------|  
|Animieren|**ACN_START**|  
|Kontrollkästchen|**BN_CLICKED**|  
|Kombinationsfeld|**CBN_SELCHANGE**|  
|Benutzerdefiniert|**TTN_GETDISPINFO**|  
|Datums-/Zeitauswahl|**DTN_DATETIMECHANGE**|  
|Eingabefeld|**EN_CHANGE**|  
|Gruppenfeld|(Nicht zutreffend)|  
|Abkürzungstaste|**NM_OUTOFMEMORY**|  
|IP-Adresse|**IPN_FIELDCHANGED**|  
|Liste|**LVN_ITEMCHANGE**|  
|Listenfeld|**LBN_SELCHANGE**|  
|Monatskalender|**MCN_SELCHANGE**|  
|Bildsteuerelement|(Nicht zutreffend)|  
|Status|**NM_CUSTOMDRAW**|  
|Push-Schaltfläche|**BN_CLICKED**|  
|Optionsfeld|**BN_CLICKED**|  
|Rich-edit|**EN_CHANGE**|  
|Bildlaufleiste|**NM_THEMECHANGED**|  
|Slider|**NM_CUSTOMDRAW**|  
|Drehfeld|**UDN_DELTAPOS**|  
|Statischer Text|(Nicht zutreffend)|  
|Registerkarte|**TCN_SELCHANGE**|  
|Struktur|**TVN_SELCHANGE**|  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Definieren von Membervariablen für Dialogfeld-Steuerelemente](../windows/defining-member-variables-for-dialog-controls.md)   
 [Mit Benutzeroberflächenobjekten verknüpfte Meldungstypen](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [Bearbeiten eines Meldungshandlers](../mfc/reference/editing-a-message-handler.md)   
 [Definieren eines Meldungshandlers für eine reflektierte Meldung](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [Deklarieren einer Variablen, die basierend auf der neuen Steuerelementklasse](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)

