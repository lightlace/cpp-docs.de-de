---
title: "CEvent Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEvent class"
  - "Synchronisierungsklassen, CEvent class"
  - "synchronization objects, event"
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: 27
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# CEvent Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt ein Ereignis dar, das ein Synchronisierungsobjekt, das einen Thread ermöglicht, andere zu benachrichtigen, dass ein Ereignis aufgetreten ist.  
  
## Syntax  
  
```  
class CEvent : public CSyncObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CEvent::CEvent](../Topic/CEvent::CEvent.md)|Erstellt ein `CEvent`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CEvent::PulseEvent](../Topic/CEvent::PulseEvent.md)|Legt das Ereignis zu verfügbarem \(signalisiert\), die Versionen, die Threads warten, und die für das Ereignis zu nicht verfügbaren fest \(nicht signalisiert\).|  
|[CEvent::ResetEvent](../Topic/CEvent::ResetEvent.md)|Legt das Ereignis zu nicht verfügbaren fest \(nicht signalisiert\).|  
|[CEvent::SetEvent](../Topic/CEvent::SetEvent.md)|Legt das Ereignis zu verfügbarem \(signalisiert\) und \- Versionen alle wartenden Threads fest.|  
|[CEvent::Unlock](../Topic/CEvent::Unlock.md)|Gibt das Ereignisobjekt frei.|  
  
## Hinweise  
 Ereignisse sind nützlich, wenn ein Thread muss wissen, wann die Aufgabe ausführt.  Beispielsweise muss ein Thread, der Daten an ein Datenarchiv kopiert, benachrichtigt, wenn neue Daten verfügbar sind.  Indem Sie ein `CEvent`\-Objekt verwenden, um die Kopie zu benachrichtigen, dennoch Sie, wenn neue Daten verfügbar sind, der Thread kann seine Aufgabe so schnell wie möglich ausführen.  
  
 `CEvent`\-Objekte haben zwei Typen: manuell und automatisch.  
  
 Ein automatisches `CEvent`\-Objekt gibt automatisch in einen nicht signalisierten \(nicht verfügbaren\) Zustand zurück, nachdem mindestens ein Thread freigegeben ist.  Standardmäßig ist ein `CEvent`\-Objekt automatisch, es sei denn, Sie `TRUE` für den `bManualReset`\-Parameter während der Erstellung übergeben.  
  
 Ein manuelles `CEvent`\-Objekt verbleibt im Zustand, der von [SetEvent](../Topic/CEvent::SetEvent.md) oder [ResetEvent](../Topic/CEvent::ResetEvent.md), bis die andere Funktion festgelegt ist, wird aufgerufen.  Um ein manuelles `CEvent`\-Objekt zu erstellen, führen Sie `TRUE` für den `bManualReset`\-Parameter während der Erstellung.  
  
 Um ein `CEvent`\-Objekt zu verwenden, erstellen Sie das Objekt `CEvent` lassen.  Geben Sie den Namen des Ereignisses, das Sie an warten möchten, und geben Sie auch an, dass die Anwendung es zuerst besitzen soll.  Sie können auf das Ereignis dann zugreifen, wenn der Konstruktor zurückkehrt.  Rufen Sie auf, um [SetEvent](../Topic/CEvent::SetEvent.md) \(\), stellen Sie dem bereit Ereignisobjekt signalisieren und [Entsperren Sie](../Topic/CEvent::Unlock.md) aufzurufen, wenn Sie auf die gesteuerte Ressource Dateizugriff durchgeführt werden.  
  
 Eine alternative Methode für die Verwendung von `CEvent`\-Objekten ist, eine Variable des Typs `CEvent` hinzuzufügen, wie ein Datenmember für die Klasse, die Sie steuern möchten.  Während der Erstellung des Objekts gesteuerten, rufen Sie den Konstruktor des `CEvent` Datenmembers auf und geben Sie, ob das Ereignis zuerst signalisiert wird, und auch specifythe Typ des Ereignisobjekts, das gewünschte, der Name des Ereignisses \(wenn über Prozessgrenzen verwendet wird\) und alle gewünschten Sicherheitsattribute an.  
  
 Um auf eine Ressource zuzugreifen, die auf diese Weise durch ein `CEvent`\-Objekt gesteuert wird, erstellen Sie entweder eine Variable des Typs [CSingleLock](../../mfc/reference/csinglelock-class.md) oder geben Sie [CMultiLock](../../mfc/reference/cmultilock-class.md) in der Zugriffsmethode der Ressource ein.  Rufen Sie dann die Methode des `Lock` Sperrenobjekts auf \(beispielsweise, [CMultiLock::Lock](../Topic/CMultiLock::Lock.md)\).  An diesem Punkt wird der Thread entweder auf die Ressource zugreifen, wartet die Ressource freigegeben werden und erhält Zugriff oder die Wartung freigegeben werden, Ressource, Timeout, und auf Fehler, die Ressource zu erhalten.  In jedem Fall ist auf die Ressource in eine threadsichere zugegriffen wurde.  Um die Ressource freigegeben wird, rufen Sie `SetEvent` auf die dem Ereignisobjekt zu signalisieren, und verwenden Sie anschließend die Methode des `Unlock` Sperrenobjekts \(beispielsweise, [CMultiLock::Unlock](../Topic/CMultiLock::Unlock.md)\), oder Sie können die Sperre Fall außerhalb des gültigen Bereichs Objekts.  
  
 Weitere Informationen dazu, wie `CEvent`\-Objekte, finden Sie unter [Multithreading: Verwendungsweise der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md) verwendet.  
  
## Beispiel  
 [!CODE [NVC_MFC_Utilities#45](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#45)]  
  
 [!CODE [NVC_MFC_Utilities#46](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#46)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## Anforderungen  
 **Header:**  afxmt.h  
  
## Siehe auch  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)