---
title: "CSemaphore Class"
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
  - "CSemaphore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSemaphore class"
  - "Semaphoren"
  - "synchronization objects, Semaphoren"
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CSemaphore Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Objekt der Klasse `CSemaphore` stellt ein "Semaphor" dar \- ein Synchronisierungsobjekt, das eine begrenzte Anzahl von Threads in einem oder mehreren Prozessen ermöglicht, auf ein zuzugreifen, behält die Anzahl der Threads an, die derzeit auf eine angegebene Ressource zugreifen.  
  
## Syntax  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSemaphore::CSemaphore](../Topic/CSemaphore::CSemaphore.md)|Erstellt ein `CSemaphore`\-Objekt.|  
  
## Hinweise  
 Semaphoren sind nützlich, wenn der Zugriff auf eine freigegebene Ressource gesteuert wird, die eine eingeschränkte Anzahl von Benutzern nur unterstützen kann.  Die aktuelle Anzahl `CSemaphore` des Objekts ist die Anzahl von zusätzlichen ermöglicht Benutzern.  Wenn die Anzahl null erreicht, werden alle Versuche, die Ressource zu verwenden, die vom Objekt gesteuert wird, **CSemaphore**  in eine Systemwarteschlange und warten bis sie entweder Timeout oder die Anzahlanstiege über 0 eingefügt.  Die maximale Anzahl von Benutzern, die auf die gesteuerte Ressource gleichzeitig zugreifen können, wird während der Erstellung des Objekts `CSemaphore` angegeben.  
  
 Um ein **CSemaphore** \-Objekt zu verwenden, erstellen Sie das Objekt `CSemaphore` wenn es erforderlich ist.  Geben Sie den Namen des Semaphors, das Sie an warten möchten an und dass die Anwendung es zuerst besitzen soll.  Sie können auf das Semaphor dann zugreifen, wenn der Konstruktor zurückkehrt.  Rufen Sie [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) auf, wenn Sie auf die gesteuerte Ressource Dateizugriff durchgeführt werden.  
  
 Eine alternative Methode für die Verwendung von `CSemaphore`\-Objekten ist, eine Variable des Typs `CSemaphore` hinzuzufügen, wie ein Datenmember für die Klasse, die Sie steuern möchten.  Während der Erstellung des Objekts gesteuerten, rufen Sie den Konstruktor des `CSemaphore` Datenmembers auf, der die ursprüngliche Zugriffsanzahl, maximale Zugriffsanzahl, Namen des Semaphors angibt \(sofern über Prozessgrenzen verwendet wird\) und gewünschte Sicherheitsattribute.  
  
 Um auf die Ressourcen zugreifen auf diese Weise, zuerst gesteuert durch `CSemaphore`\-Objekte entweder eine Variable des Typs [CSingleLock](../../mfc/reference/csinglelock-class.md) zu erstellen oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in der Zugriffsmemberfunktion der Ressource einzugeben.  Rufen Sie dann die `Lock`\-Memberfunktion des Sperrobjekts auf \(beispielsweise [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\).  An diesem Punkt wird der Thread entweder auf die Ressource zugreifen, wartet die Ressource freigegeben werden und erhält Zugriff oder Wartung die Ressource freigegeben werden, und auf Timeout und kann die Ressource erlangt nicht.  In jedem Fall ist auf die Ressource in eine threadsichere zugegriffen wurde.  Um die Ressource freigeben, verwenden Sie die `Unlock`\-Memberfunktion des Sperrobjekts \(beispielsweise [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)\), oder das Objekt dem Fall außerhalb des gültigen Bereichs ermöglichen.  
  
 Alternativ können Sie ein eigenständiges **CSemaphore** \-Objekt erstellen und vor dem Versuch greifen darauf explizit, auf die gesteuerte Ressource zuzugreifen zu.  Diese Methode, während klarer an jemanden, das den Quellcode lesen, ist fehleranfälliger.  
  
 Weitere Informationen dazu, wie **CSemaphore** \-Objekte, finden Sie im Artikel [Multithreading: Erstellen der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md) verwendet.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## Anforderungen  
 **Header:**  afxmt.h  
  
## Siehe auch  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)