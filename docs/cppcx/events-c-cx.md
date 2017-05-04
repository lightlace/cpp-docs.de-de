---
title: "Ereignisse (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 31c8e08a-00ad-40f9-8f7e-124864aaad58
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# Ereignisse (C++/CX)
Ein [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typ kann Ereignisse deklarieren \(d. h. veröffentlichen\), und Clientcode in der gleichen Komponente oder in anderen Komponenten kann diese Ereignisse durch die Zuordnung von Methoden, sogenannten *Ereignishandlern* mit dem Ereignis abonnieren. Mehrere Ereignishandler können einem einzelnen Ereignis zugeordnet werden. Wenn das Veröffentlichungsobjekt das Ereignis auslöst, werden alle Ereignishandler aufgerufen. Auf diese Weise kann eine abonnierende Klasse eine beliebige geeignete benutzerdefinierte Aktion durchführen, wenn der Herausgeber das Ereignis auslöst. Ein Ereignis hat einen Delegattyp, der die Signatur angibt, die alle Ereignishandler verwenden, um das Ereignis zu abonnieren.  
  
## Verwenden von Ereignissen in den Windows\-Komponenten  
 Viele Komponenten in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] machen Ereignisse verfügbar. Beispielsweise löst ein LightSensor\-Objekt ein ReadingChanged\-Ereignis aus, wenn der Sensor einen neuen Lumineszenzwert meldet. Wenn Sie ein LightSensor\-Objekt im Programm verwenden, können Sie eine Methode definieren, die aufgerufen wird, wenn das ReadingChanged\-Ereignis ausgelöst wird. Die Methode kann alle von Ihnen gewünschten Aktionen ausführen. Die einzige Voraussetzung ist, dass die Signatur mit der Signatur des Delegaten übereinstimmen muss. Weitere Informationen zum Erstellen eines Delegatereignishandlers und zum Abonnieren eines Ereignisses finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md).  
  
## Erstellen von benutzerdefinierten Ereignissen  
  
### Deklaration  
 Sie können ein Ereignis in einer Verweisklasse oder einer Schnittstelle deklarieren, und der Zugriff darauf kann öffentlich, intern \(öffentlich\/privat\), öffentlich geschützt, geschützt, privat geschützt oder privat sein. Wenn Sie ein Ereignis deklarieren, erstellt der Compiler intern ein Objekt, das zwei Accessormethoden bereitstellt: Hinzufügen und Entfernen. Registrieren Sie beim Abonnieren von Objekten Ereignishandler. Das Ereignisobjekt speichert sie in einer Sammlung. Wenn ein Ereignis ausgelöst wird, ruft das Ereignisobjekt wiederum alle Handler in der Liste auf. Ein triviales Ereignis – wie das im folgenden Beispiel – hat einen impliziten Auslagerungsspeicher sowie implizite `add`\- und `remove`\-Accessormethoden. Sie können auch eigene Accessoren angeben, ebenso wie Sie benutzerdefinierte `get`\- und `set`\-Accessoren für eine Eigenschaft angeben können.  Die implementierende Klasse kann die Ereignisabonnentenliste bei einem trivialen Ereignis nicht manuell durchlaufen.  
  
 Im folgenden Beispiel werden die Deklaration und das Auslösen einer Schnittstelle erläutert. Beachten Sie, dass das Ereignis über einen Delegattyp verfügt und deklariert wird, indem Sie das "^"\-Symbol verwendet wird.  
  
 [!code-cpp[cx_events#01](../snippets/cpp/VS_Snippets_Misc/cx_events/cpp/cx_events/class1.h#01)]  
  
### Verwendung  
 Im folgenden Beispiel wird gezeigt, wie der `+=`\-Operator von einer abonnierenden Klasse verwendet wird, um das Ereignis zu abonnieren, und wie ein Ereignishandler bereitgestellt wird, der ausgeführt wird, wenn das Ereignis ausgelöst wird. Beachten Sie, dass die bereitstellende Funktion der Signatur des Delegaten entspricht, der auf der Herausgeberseite im `EventTest`\-Namespace definiert ist.  
  
 [!code-cpp[cx_events#02](../snippets/cpp/VS_Snippets_Misc/cx_events/cpp/eventsupportinvs/eventclientclass.h#02)]  
  
> [!WARNING]
>  Im Allgemeinen empfiehlt es sich, eine benannte Funktion statt eines Lambda\-Ausdrucks für einen Ereignishandler zu verwenden. Andernfalls müssen Sie sorgfältig darauf achten, Zirkelverweise zu vermeiden. Eine benannte Funktion übernimmt den this\-Zeiger als schwachen Verweis, während ein Lambda den this\-Zeiger als starken Verweis übernimmt und einen Zirkelverweis erstellt. Weitere Informationen finden Sie unter [Weak references and breaking cycles \(C\+\+\/CX\)](../cppcx/weak-references-and-breaking-cycles-c-cx.md).  
  
### Benutzerdefinierte Hinzufügen\- und Entfernen\-Methoden  
 Intern verfügt ein Ereignis über eine add\-Methode, eine remove\-Methode und eine raise\-Methode. Wenn Clientcode ein Ereignis abonniert, wird die add\-Methode aufgerufen und der übergebene Delegat der Aufrufliste des Ereignisses hinzugefügt. Die Veröffentlichungsklasse ruft das Ereignis auf, dadurch wird die raise\(\)\-Methode aufgerufen, und jeder Delegat in der Liste wird wiederum aufgerufen. Ein Abonnent kann sich selbst aus der Delegatliste entfernen, wodurch die remove\-Methode des Ereignisses aufgerufen wird. Der Compiler stellt Standardversionen dieser Methoden bereit, wenn Sie sie nicht im Code definieren. Diese werden als triviale Ereignisse bezeichnet. In vielen Fällen ist nur ein triviales Ereignis erforderlich.  
  
 Sie können benutzerdefinierte Hinzufügen\-, Entfernen\- und Auslösen\-Methoden für ein Ereignis angeben, wenn Sie benutzerdefinierte Logik als Reaktion auf das Hinzufügen oder Entfernen von Abonnenten ausführen müssen. Wenn Sie beispielsweise über ein teures Objekt verfügen, das nur für die Ereignisberichterstellung erforderlich ist, können Sie die Erstellung des Objekts verzögern, bis ein Client tatsächlich das Ereignis abonniert.  
  
 Im nächsten Beispiel wird veranschaulicht, wie Sie benutzerdefinierte Hinzufügen\-, Entfernen\- und Auslösen\-Methoden zu einem Ereignis hinzufügen können.  
  
 [!code-cpp[cx_events#03](../snippets/cpp/VS_Snippets_Misc/cx_events/cpp/cx_events/class1.h#03)]  
  
## Entfernen eines Ereignishandlers von der Abonnentenseite  
 In einigen wenigen Fällen möchten Sie vielleicht einen Ereignishandler für ein Ereignis entfernen, das Sie zuvor abonniert hatten. Sie möchten es beispielsweise durch einen anderen Ereignishandler ersetzen oder einige Ressourcen löschen, die durch diesen Ereignishandler gehalten werden. Um einen Handler zu entfernen, müssen Sie das von der `+=`\-Operation zurückgegebene EventRegistrationToken speichern. Sie können den `-=`\-Operator im Token dann verwenden, um einen Ereignishandler zu entfernen.  Allerdings kann der ursprüngliche Handler noch aufgerufen werden, nachdem er entfernt wurde. Wenn Sie beabsichtigen, einen Ereignishandler zu entfernen, erstellen Sie daher einen Memberflag und setzen Sie diesen, wenn das Ereignis entfernt wird. Aktivieren Sie dann im Ereignishandler den Flag und kehren Sie sofort zurück, wenn der Flag gesetzt wird. Das grundlegende Muster wird im nächsten Beispiel veranschaulicht.  
  
 [!code-cpp[cx_events#04](../snippets/cpp/VS_Snippets_Misc/cx_events/cpp/eventsupportinvs/eventclientclass.h#04)]  
  
## Hinweise  
 Mehrere Handler können demselben Ereignis zugeordnet werden. Die Ereignisquelle ruft sequenziell alle Ereignishandler von dem gleichen Thread auf. Wenn ein Ereignisempfänger innerhalb der Ereignishandlermethode blockiert, blockiert den Aufruf anderer Ereignishandler für dieses Ereignis durch die Ereignisquelle.  
  
 Die Reihenfolge, in der die Ereignisquelle Ereignishandler auf Ereignisempfängern aufruft, wird nicht garantiert und unterscheidet sich von Aufruf zu Aufruf.  
  
## Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Delegaten](../cppcx/delegates-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)