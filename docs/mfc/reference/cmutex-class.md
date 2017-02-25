---
title: "CMutex Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "Mutex"
  - "CMutex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMutex class"
  - "mutex"
  - "Synchronisierungsklassen, CMutex class"
  - "synchronization objects, mutex"
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMutex Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Mutex "" \- ein Synchronisierungsobjekt, das Threads gegenseitig ausschließenden Zugriff auf eine Ressource dar.  
  
## Syntax  
  
```  
class CMutex : public CSyncObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMutex::CMutex](../Topic/CMutex::CMutex.md)|Erstellt ein `CMutex`\-Objekt.|  
  
## Hinweise  
 Mutexe sind nützlich, wenn nur einen Thread auf einmal ermöglicht werden kann, um Daten oder eine andere gesteuerte Ressource zu ändern.  Beispielsweise Knoten zu einer verknüpften Liste hinzuzufügen ist ein Prozess, der durch einen Thread nur jeweils ausgeführt werden dürfen.  Durch ein `CMutex`\-Objekt verwendet, um die verknüpfte Liste zu steuern, kann nur ein Thread zur Liste auf einmal verschaffen.  
  
 Um ein `CMutex`\-Objekt zu verwenden, erstellen Sie das Objekt `CMutex` wenn es erforderlich ist.  Geben Sie den Namen der Mutex, die Sie an warten möchten an und dass die Anwendung ihn zunächst besitzen soll.  Sie können auf die Mutex dann zugreifen, wenn der Konstruktor zurückkehrt.  Rufen Sie [CSyncObject::Unlock](../Topic/CSyncObject::Unlock.md) auf, wenn Sie auf die gesteuerte Ressource Dateizugriff durchgeführt werden.  
  
 Eine alternative Methode für die Verwendung von `CMutex`\-Objekten ist, eine Variable des Typs `CMutex` hinzuzufügen, wie ein Datenmember für die Klasse, die Sie steuern möchten.  Während der Erstellung des Objekts gesteuerten, rufen Sie den Konstruktor des `CMutex` Datenmemberangebens, wenn der Mutex zuerst gehört, des Namens der Mutex \(sofern über Prozessgrenzen verwendet wird\) und der gewünschten Sicherheitsattribute auf.  
  
 Um auf die Ressourcen zugreifen auf diese Weise, zuerst gesteuert durch `CMutex`\-Objekte entweder eine Variable des Typs [CSingleLock](../../mfc/reference/csinglelock-class.md) zu erstellen oder [CMultiLock](../../mfc/reference/cmultilock-class.md) in der Zugriffsmemberfunktion der Ressource einzugeben.  Rufen Sie dann die `Lock`\-Memberfunktion des Sperrobjekts auf \(beispielsweise [CSingleLock::Lock](../Topic/CSingleLock::Lock.md)\).  An diesem Punkt wird der Thread entweder auf die Ressource zugreifen, wartet die Ressource freigegeben werden und erhält Zugriff oder Wartung die Ressource freigegeben werden, und auf Timeout und kann die Ressource erlangt nicht.  In jedem Fall ist auf die Ressource in eine threadsichere zugegriffen wurde.  Um die Ressource freigeben, verwenden Sie die `Unlock`\-Memberfunktion des Sperrobjekts \(beispielsweise [CSingleLock::Unlock](../Topic/CSingleLock::Unlock.md)\), oder das Objekt dem Fall außerhalb des gültigen Bereichs ermöglichen.  
  
 Weitere Informationen zur Verwendung von `CMutex`\-Objekten, finden Sie im Artikel [Multithreading: Erstellen der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## Anforderungen  
 **Header:**  afxmt.h  
  
## Siehe auch  
 [CSyncObject Class](../../mfc/reference/csyncobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)