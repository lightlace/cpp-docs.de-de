---
title: 'TN070: MFC-Fensterklassennamen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.classes
dev_langs:
- C++
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 183fd4c76fc8df092c5b7740ff5de2e35b64d682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn070-mfc-window-class-names"></a>TN070: MFC-Fensterklassennamen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 MFC-Fenster verwenden einen dynamisch erstellte Klassennamen, der die Funktionen des Fensters wiedergibt. MFC generiert Klassennamen dynamisch für Rahmenfenster, Ansichten und Popup-Fenster, die von der Anwendung erstellt. Dialogfelder und Steuerelemente, die von einer MFC_Anwendung erstellt haben Windows bereitgestellten Namen für die betreffende Fenster-Klasse.  
  
 Sie können den dynamisch angegebenen Klassennamen ersetzen, indem Sie eigene Fensterklasse registriert, und verwenden ihn in einer Überschreibung von [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow). Ihre MFC bereitgestellten Klassennamen entsprechen der beiden folgenden Formen:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 Die hexadezimalen Ziffern, das Ersetzen der `%x` Zeichen werden von den Daten gefüllt der [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur. MFC verwendet dieses Verfahren, damit mehrere C++-Klassen, die identische erfordern **WNDCLASS** Strukturen können die gleichen registrierten Fensterklasse freigeben. Im Gegensatz zu den meisten einfache Win32-Anwendungen, MFC-Anwendungen haben nur eine **WNDPROC**, sodass Sie problemlos freigeben können **WNDCLASS** auszugeben, um die Zeit und Speicherplatz zu speichern. Die ersetzbaren Werte für die `%x` Zeichen, die oben gezeigte lauten wie folgt:  
  
- **WNDCLASS.hInstance**  
  
- **WNDCLASS.style**  
  
- **WNDCLASS.hCursor**  
  
- **WNDCLASS.hbrBackground**  
  
- **WNDCLASS.hIcon**  
  
 Die erste Form (`Afx:%x:%x`) wird verwendet, wenn **hCursor**, **HbrBackground**, und **hIcon** sind alle **NULL**.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorie](../mfc/technical-notes-by-category.md)   
 [TN020: ID-Benennungs- und Nummerierungskonventionen](../mfc/tn020-id-naming-and-numbering-conventions.md)

