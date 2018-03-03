---
title: "Handler für Windows-Standardmeldungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afx_msg
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91df3462297c2a45a8938d815cc3b6a3b8ca6edb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-standard-windows-messages"></a>Handler für Windows-Standardmeldungen
Standard-Handler für standard-Windows-Meldungen (**WM_**) sind in Klasse vordefiniert `CWnd`. Die Klassenbibliothek Basen Namen für diese Handler auf den Nachrichtennamen. Z. B. der Handler für das `WM_PAINT` Nachricht im deklarierten `CWnd` als:  
  
 `afx_msg void OnPaint();`  
  
 Die **Afx_msg** Schlüsselwort schlägt vor, Ihnen die Auswirkungen der C++-Komponente **virtuellen** Schlüsselwort, indem die Handler von anderen unterschieden `CWnd` Memberfunktionen. Beachten Sie jedoch, dass diese Funktionen nicht tatsächlich virtuelle sind; Sie werden stattdessen über meldungszuordnungen implementiert. Meldungszuordnungen richten sich ausschließlich auf standard Präprozessormakros und nicht für alle Erweiterungen der Programmiersprache C++. Die **Afx_msg** Schlüsselwort in Leerzeichen aufgelöst wird, nach der vorverarbeitung.  
  
 Um einen Handler definiert, die in einer Basisklasse zu überschreiben, definieren Sie einfach eine Funktion mit den gleichen Prototyp, in der abgeleiteten Klasse und einen meldungszuordnung Eintrag für den Handler vornehmen. Der Handler überschreibt"" ein Handler mit dem gleichen Namen in einer der Basisklassen der Klasse.  
  
 In einigen Fällen sollte der Handler den überschriebenen Handler in der Basisklasse aufrufen, damit die Basisklasse(n) und das Fenster für die Nachricht ausgeführt werden können. In denen Sie den Basisklassen-Handler in der Überschreibung aufrufen, hängt von den Umständen ab. In einigen Fällen müssen Sie rufen zuerst den Basisklassen-Handler und manchmal last. In einigen Fällen rufen Sie die Basisklasse Handler bedingt, wenn Sie nicht die Nachricht selbst behandeln. In einigen Fällen sollten Sie den Handler der Basisklasse aufrufen und anschließend bedingt auszuführen, eine eigene Handlercode, je nach Wert oder von der Basisklasse-Handler zurückgegeben wurden.  
  
> [!CAUTION]
>  Es ist nicht sicher ist, ändern die Argumente, die an einen Ereignishandler übergeben werden, wenn Sie beabsichtigen, die sie auf einen Basisklassen-Handler zu übergeben. Ändern möchten, z. B. möglicherweise die `nChar` Argument der `OnChar` Handler (in Großbuchstaben zu konvertieren, z. B.). Dieses Verhalten ist ziemlich kryptische, aber wenn Sie diesen Effekt zu erzielen verwenden die `CWnd` Memberfunktion **SendMessage** stattdessen.  
  
 Wie Sie das richtige Verfahren für eine bestimmte Nachricht überschrieben werden, wenn das Eigenschaftenfenster des Grundgerüsts die Handlerfunktion für eine bestimmte Nachricht schreibt bestimmen – ein `OnCreate` Handler für `WM_CREATE`, z. B. – es Skizzen in Form von den empfohlenen überschreiben die Memberfunktion. Im folgende Beispiel empfiehlt die der Handler zuerst den Handler der Basisklasse aufrufen, und fahren Sie fort, nur, wenn er nicht-1 zurückgibt.  
  
 [!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]  
  
 Beginnen gemäß der Konvention werden die Namen dieser Handler mit dem Präfix "On". Einige dieser Handler akzeptieren keine Argumente, während andere mehrere verwenden können. Einige haben auch einen Rückgabetyp außer `void`. Die Standardhandler für alle **WM_** Nachrichten werden in dokumentiert die *MFC-Referenz* als Memberfunktionen der Klasse `CWnd` , deren Namen beginnen mit "Weiter". In den memberfunktionsdeklarationen `CWnd` vorangestellt **Afx_msg**.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
