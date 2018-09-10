---
title: Standard Steuerelementereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7a57cb6c72d7d444c345140f4a738a3d4a3232c0
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315612"
---
# <a name="default-control-events"></a>Standardereignisse für Steuerelemente

Die folgenden Steuerelementnamen haben die Standard-Hinweise:

|Steuerelementname|Standardereignis|
|------------------|-------------------|
|Animieren|ACN_START|
|Kontrollkästchen|BN_CLICKED|
|Kombinationsfeld|CBN_SELCHANGE|
|Benutzerdefiniert|TTN_GETDISPINFO|
|Datums-/ Zeitauswahl|DTN_DATETIMECHANGE|
|Bearbeitungsfeld|EN_CHANGE-EREIGNIS|
|Gruppenfeld|(Nicht zutreffend)|
|Abkürzungstaste|NM_OUTOFMEMORY|
|IP-Adresse|IPN_FIELDCHANGED|
|Liste|LVN_ITEMCHANGE|
|Listenfeld|LBN_SELCHANGE|
|Monatskalender|MCN_SELCHANGE|
|Bildsteuerelement|(Nicht zutreffend)|
|Status|NM_CUSTOMDRAW|
|Schaltfläche|BN_CLICKED|
|Optionsfeld|BN_CLICKED|
|Rich-edit|EN_CHANGE-EREIGNIS|
|Bildlaufleiste|NM_THEMECHANGED|
|Slider|NM_CUSTOMDRAW|
|Drehfeld|UDN_DELTAPOS|
|Statischer Text|(Nicht zutreffend)|
|Registerkarte|TCN_SELCHANGE|
|Struktur|TVN_SELCHANGE|

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Definieren von Membervariablen für Dialogfeld-Steuerelemente](../windows/defining-member-variables-for-dialog-controls.md)  
[Mit Benutzeroberflächenobjekten verknüpfte Meldungstypen](../mfc/reference/message-types-associated-with-user-interface-objects.md)  
[Bearbeiten eines Meldungshandlers](../mfc/reference/editing-a-message-handler.md)  
[Definieren eines Meldungshandlers für eine reflektierte Meldung](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)  
[Deklarieren einer auf der neuen Steuerelementklasse basierenden Variable](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)  
[Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)