---
title: "Gewusst wie: Erstellen und Verwenden von CComPtr- und CComQIPtr-Instanzen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: b0356cfb-12cc-4ee8-b988-8311ed1ab5e0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen und Verwenden von CComPtr- und CComQIPtr-Instanzen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der klassischen Windows\-Programmierung werden Bibliotheken häufig als COM\-Objekte \(oder genauer gesagt, als COM\-Server\) implementiert. Viele Windows\-Betriebssystemkomponenten werden als COM\-Server implementiert, und viele Mitwirkende bieten Bibliotheken in dieser Form. Informationen zu den COM\-Grundlagen finden Sie unter [Component Object Model \(COM\)](assetId:///3578ca42-a4b6-44b3-ad5b-aeb5fa61f3f4).  
  
 Speichern Sie beim Instanziieren eines Component Object Model\-Objekts \(COM\) den Schnittstellenzeiger in einem intelligenten COM\-Zeiger, der die Zählung von Verweisen mit Aufrufen von `AddRef` und `Release` im Destruktor durchführt. Wenn Sie die Active Template Library \(ATL\) oder die Microsoft Foundation Class\-Bibliothek \(MFC\-Bibliothek\) verwenden, verwenden Sie den intelligenten `CComPtr`\-Zeiger. Wenn Sie ATL bzw. MFC nicht verwenden, verwenden Sie `_com_ptr_t`. Da es kein COM\-Äquivalent zu `std::unique_ptr` gibt, verwenden Sie diese intelligenten Zeiger sowohl für Szenarien mit einzelnen als auch mehreren Besitzern. Sowohl `CComPtr` als auch `ComQIPtr` unterstützt Verschiebungsvorgänge mit rvalue\-Verweisen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie `CComPtr` verwenden, um ein COM\-Objekt zu instanziieren und Zeiger auf seine Schnittstellen abzurufen. Beachten Sie, dass die Memberfunktion `CComPtr::CoCreateInstance` anstelle der Win32\-Funktion gleichen Namens verwendet wird, um das COM\-Objekt zu erstellen.  
  
 [!CODE [COM_smart_pointers#01](../CodeSnippet/VS_Snippets_Cpp/com_smart_pointers#01)]  
  
 `CComPtr` und die zugehörigen Elemente sind Teil der ATL und in „atlcomcli.h“ definiert.`_com_ptr_t` wird in „comip.h“ deklariert. Der Compiler erstellt Spezialisierungen von `_com_ptr_t`, wenn er Wrapperklassen für Typbibliotheken generiert.  
  
## Beispiel  
 ATL stellt auch `CComQIPtr` bereit, der eine einfachere Syntax verwendet, um ein COM\-Objekt zum Abrufen einer zusätzlichen Schnittstelle abzufragen. Wir empfehlen jedoch `CComPtr`, da er alles beherrscht, was `CComQIPtr` kann, und semantisch mehr mit unformatierten COM\-Schnittstellenzeigern übereinstimmt. Bei Verwendung eines `CComPtr` zum Abfragen einer Schnittstelle wird der neue Schnittstellenzeiger in einem Ausgabeparameter platziert. Wenn bei dem Aufruf ein Fehler auftritt, wird HRESULT – das normale COM\-Muster – zurückgegeben. Mit `CComQIPtr` ist der Zeiger selbst der Rückgabewert, und wenn bei dem Aufruf ein Fehler auftritt, ist kein Zugriff auf den internen HRESULT\-Rückgabewert möglich. Die folgenden beiden Zeilen zeigen, wie sich die Fehlerbehandlungsmechanismen in `CComPtr` und `CComQIPtr` unterscheiden.  
  
 [!CODE [COM_smart_pointers#02](../CodeSnippet/VS_Snippets_Cpp/com_smart_pointers#02)]  
  
## Beispiel  
 `CComPtr` bietet eine Spezialisierung für IDispatch, die das Speichern von Zeigern in COM\-Automatisierungskomponenten und das Aufrufen der Methoden über die Schnittstelle mit später Bindung ermöglicht.`CComDispatchDriver` ist eine Typedef für `CComQIPtr<IDispatch, &IIDIDispatch>`, die implizit in `CComPtr<IDispatch>` konvertierbar ist. Daher ist jeder dieser drei Namen äquivalent zu `CComPtr<IDispatch>`, wenn er im Code vorkommt. Das folgende Beispiele zeigt das Abrufen eines Zeigers in das Microsoft Word\-Objektmodell mit Verwendung eines `CComPtr<IDispatch>`.  
  
 [!CODE [COM_smart_pointers#03](../CodeSnippet/VS_Snippets_Cpp/com_smart_pointers#03)]  
  
## Siehe auch  
 [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)