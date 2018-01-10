---
title: Mit benutzerdefinierten Formatzeichenfolgen in einem Datums- und Zeitauswahl Steuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfaad06571a8648db24497c46d55cb2eb1ce2157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Verwenden von benutzerdefinierten Formatzeichenfolgen in einem Steuerelement für die Datums- und Zeitauswahl
Standardmäßig bieten Picker-Steuerelemente für Datum und Uhrzeit an, dass die drei Typen (jedes Format entspricht, um eine eindeutige Format) für die Anzeige die aktuellen Datums- oder Zeitangabe zu formatieren:  
  
-   **DTS_LONGDATEFORMAT** zeigt das Datum im langen Format Ausgabe wie "Mittwoch, 3. Januar 2000".  
  
-   **DTS_SHORTDATEFORMAT** zeigt das Datum im kurzen Format Ausgabe z. B. "1/3/00".  
  
-   **DTS_TIMEFORMAT** zeigt die Uhrzeit im langen Format Ausgabe wie "5:31:42 PM".  
  
 Allerdings können Sie die Darstellung von Datum oder Uhrzeit anpassen, indem Sie eine benutzerdefinierte Formatzeichenfolge verwenden. Diese benutzerdefinierte Zeichenfolge besteht aus vorhandenen Formatzeichen, Nonformat Zeichen oder eine Kombination aus beidem. Nachdem die benutzerdefinierte Zeichenfolge erstellt wurde, stellen Sie einen Aufruf von [CDateTimeCtrl:: setFormat initialisiert](../mfc/reference/cdatetimectrl-class.md#setformat) in Ihre benutzerdefinierte Zeichenfolge übergeben. Die Datums- / Zeitauswahl-Steuerelement wird den aktuellen Wert, der mit der benutzerdefinierten Formatzeichenfolge angezeigt.  
  
 Der folgende Beispielcode (wobei `m_dtPicker` ist die `CDateTimeCtrl` Objekt) zeigt eine mögliche Lösung:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 Zusätzlich zu benutzerdefinierten Formatzeichenfolgen Steuerelemente Datums- / Zeitauswahl auch unterstützen [Rückruffeldern](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

