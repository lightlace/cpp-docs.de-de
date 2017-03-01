---
title: Meldung Makros (MFC) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f890e0675be58c8e20e313bea54b4145e2ce0bf3
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-mfc"></a>Meldungszuordnungsmakros (MFC)
Um den meldungszuordnungen zu unterstützen, stellt MFC die folgenden Makros:  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>Message-Deklaration und Demarkation Makros  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](http://msdn.microsoft.com/library/c225e7e0-a81b-495c-97f9-3e0aa1f65036)|Deklariert, dass eine Zuordnung für die Nachricht in einer Klasse verwendet wird, Nachrichten Funktionen zuzuordnen (muss in der Klassendeklaration verwendet werden).|  
|[BEGIN_MESSAGE_MAP](http://msdn.microsoft.com/library/d9201e18-04e0-4639-9810-f15768627fc2)|Der Beginn der Definition einer Nachricht Zuordnung (muss in der klassenimplementierung verwendet werden).|  
|[END_MESSAGE_MAP](http://msdn.microsoft.com/library/40f611f1-a3b4-4097-b683-091bf7cfab8b)|Beendet die Definition einer Nachricht Zuordnung (muss in der klassenimplementierung verwendet werden).|  
  
### <a name="message-mapping-macros"></a>Zuordnung Makros  
  
|||  
|-|-|  
|[ON_COMMAND](http://msdn.microsoft.com/library/f24f8bda-2cf4-49d5-aa3d-6f2e6bb003f2)|Gibt an, welche Funktion eine Nachricht angegebene Befehl behandelt.|  
|[ON_CONTROL](http://msdn.microsoft.com/library/2cb7ebdf-296b-4606-b191-3449835003db)|Gibt an, welche Funktion angegebenen Steuerelement-Benachrichtigung behandelt.|  
|[ON_MESSAGE](http://msdn.microsoft.com/library/e2faeb13-9f6e-4c0d-9f6d-b2e141a0db1e)|Gibt an, welche Funktion eine benutzerdefinierte Nachricht behandelt.|  
|[ON_OLECMD](http://msdn.microsoft.com/library/6c86327c-3d48-42ac-9dae-e0ccd3a81793)|Gibt an, welche Funktion einen Menübefehl DocObject oder Containers behandelt.|  
|[ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d)|Gibt an, welche Funktion eine registrierte benutzerdefinierte Nachricht behandelt.|  
|[ON_REGISTERED_THREAD_MESSAGE](http://msdn.microsoft.com/library/3f598bc2-b2f0-410f-8ba0-7714502170f3)|Gibt an, welche Funktion eine registrierte benutzerdefinierte Nachricht behandelt, wenn Sie haben eine `CWinThread` Klasse.|  
|[ON_THREAD_MESSAGE](http://msdn.microsoft.com/library/f718f47a-d5b1-4514-914b-e3fe2d919003)|Gibt an, welche Funktion bei eine benutzerdefinierten Meldung behandelt eine `CWinThread` Klasse.|  
|[ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)|Gibt an, welche Funktion eine angegebenen Benutzeroberflächen-Update-Befehlsnachricht behandelt.|  
  
### <a name="message-map-range-macros"></a>Meldungszuordnung Bereich-Makros  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](http://msdn.microsoft.com/library/c52719fc-dd6e-48c9-af79-383f48d608e0)|Gibt an, welche Funktion den Bereich der Befehls-IDs, die in den ersten beiden Parameter für das Makro behandelt.|  
|[ON_UPDATE_COMMAND_UI_RANGE](http://msdn.microsoft.com/library/b7105bf1-44ad-4b00-b947-31478f964729)|Gibt an, welche Aktualisierungshandler den Bereich der Befehls-IDs, die in den ersten beiden Parameter für das Makro behandelt.|  
|[ON_CONTROL_RANGE](http://msdn.microsoft.com/library/46f0e1bb-569b-4b8b-9b80-89701d1cd7fd)|Gibt an, welche Funktion Benachrichtigungen aus dem Bereich von Steuerelement-IDs, die in der zweiten und dritten Parameter für das Makro angegebenen behandelt. Der erste Parameter ist eine Steuerelement-Benachrichtigung, wie z. B. **BN_CLICKED**.|  
  
 Informationen auf meldungszuordnungen, die Message-Deklaration und Abgrenzung Makros und die Makros, die Zuordnung von Nachrichten finden Sie unter [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md) und [Nachrichtenbehandlung und Zuordnung Themen](../../mfc/message-handling-and-mapping.md). Weitere Informationen zu Meldungszuordnungsbereiche, finden Sie unter [Handler für Meldungszuordnungsbereiche](../../mfc/handlers-for-message-map-ranges.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)



