---
title: Ereignisse (C + c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 31c8e08a-00ad-40f9-8f7e-124864aaad58
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98231f0803270a9e033529e163ff2cc23cdd64e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089637"
---
# <a name="events-ccx"></a>Ereignisse (C++/CX)
Ein Windows-Runtime Typ deklarieren, kann (die veröffentlichen, hat) Ereignisse, und Clientcode in der gleichen Komponente oder in anderen Komponenten kann diese Ereignisse abonnieren, indem Sie die Zuordnung von Methoden, die aufgerufen *Ereignishandler* mit dem Ereignis. Mehrere Ereignishandler können einem einzelnen Ereignis zugeordnet werden. Wenn das Veröffentlichungsobjekt das Ereignis auslöst, werden alle Ereignishandler aufgerufen. Auf diese Weise kann eine abonnierende Klasse eine beliebige geeignete benutzerdefinierte Aktion durchführen, wenn der Herausgeber das Ereignis auslöst. Ein Ereignis hat einen Delegattyp, der die Signatur angibt, die alle Ereignishandler verwenden, um das Ereignis zu abonnieren.  
  
## <a name="consuming-events-in-windows-components"></a>Verwenden von Ereignissen in den Windows-Komponenten  
 Viele Komponenten in Windows-Runtime machen Ereignisse verfügbar. Beispielsweise löst ein LightSensor-Objekt ein ReadingChanged-Ereignis aus, wenn der Sensor einen neuen Lumineszenzwert meldet. Wenn Sie ein LightSensor-Objekt im Programm verwenden, können Sie eine Methode definieren, die aufgerufen wird, wenn das ReadingChanged-Ereignis ausgelöst wird. Die Methode können Sie dies wünschen alle von Ihnen gewünschten Aktionen ausführen; die einzige Voraussetzung ist, dass die Signatur die Signatur des Delegaten, die Weitere Informationen zum Erstellen eines delegatereignishandlers übereinstimmen muss und zum Abonnieren eines Ereignisses finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md).  
  
## <a name="creating-custom-events"></a>Erstellen von benutzerdefinierten Ereignissen  
  
### <a name="declaration"></a>Deklaration  
 Sie können ein Ereignis in einer Verweisklasse oder einer Schnittstelle deklarieren, und der Zugriff darauf kann öffentlich, intern (öffentlich/privat), öffentlich geschützt, geschützt, privat geschützt oder privat sein. Wenn Sie ein Ereignis deklarieren, erstellt der Compiler intern ein Objekt, das zwei Accessormethoden bereitstellt: Hinzufügen und Entfernen. Registrieren Sie beim Abonnieren von Objekten Ereignishandler. Das Ereignisobjekt speichert sie in einer Sammlung. Wenn ein Ereignis ausgelöst wird, ruft das Ereignisobjekt wiederum alle Handler in der Liste auf. Ein triviales Ereignis – wie das im folgenden Beispiel – hat einen impliziten Auslagerungsspeicher sowie implizite `add` - und `remove` -Accessormethoden. Sie können auch eigene Accessoren angeben, ebenso wie Sie benutzerdefinierte `get` - und `set` -Accessoren für eine Eigenschaft angeben können.  Die implementierende Klasse kann die Ereignisabonnentenliste bei einem trivialen Ereignis nicht manuell durchlaufen.  
  
 Im folgenden Beispiel werden die Deklaration und das Auslösen einer Schnittstelle erläutert. Beachten Sie, dass das Ereignis über einen Delegattyp verfügt und deklariert wird, indem Sie das "^"-Symbol verwendet wird.  
  
 [!code-cpp[cx_events#01](../cppcx/codesnippet/CPP/cx_events/class1.h#01)]  
  
### <a name="usage"></a>Verwendung  
 Im folgenden Beispiel wird gezeigt, wie der `+=` -Operator von einer abonnierenden Klasse verwendet wird, um das Ereignis zu abonnieren, und wie ein Ereignishandler bereitgestellt wird, der ausgeführt wird, wenn das Ereignis ausgelöst wird. Beachten Sie, dass die bereitstellende Funktion der Signatur des Delegaten entspricht, der auf der Herausgeberseite im `EventTest` -Namespace definiert ist.  
  
 [!code-cpp[cx_events#02](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#02)]  
  
> [!WARNING]
>  Im Allgemeinen empfiehlt es sich, eine benannte Funktion statt eines Lambda-Ausdrucks für einen Ereignishandler zu verwenden. Andernfalls müssen Sie sorgfältig darauf achten, Zirkelverweise zu vermeiden. Eine benannte Funktion übernimmt den this-Zeiger als schwachen Verweis, während ein Lambda den this-Zeiger als starken Verweis übernimmt und einen Zirkelverweis erstellt. Weitere Informationen finden Sie unter [Weak references and breaking cycles (C++/CX)](../cppcx/weak-references-and-breaking-cycles-c-cx.md).  
  
### <a name="custom-add-and-remove-methods"></a>Benutzerdefinierte Hinzufügen- und Entfernen-Methoden  
 Intern verfügt ein Ereignis über eine add-Methode, eine remove-Methode und eine raise-Methode. Wenn Clientcode ein Ereignis abonniert, wird die add-Methode aufgerufen und der übergebene Delegat der Aufrufliste des Ereignisses hinzugefügt. Die Veröffentlichungsklasse ruft das Ereignis auf, dadurch wird die raise()-Methode aufgerufen, und jeder Delegat in der Liste wird wiederum aufgerufen. Ein Abonnent kann sich selbst aus der Delegatliste entfernen, wodurch die remove-Methode des Ereignisses aufgerufen wird. Der Compiler stellt Standardversionen dieser Methoden bereit, wenn Sie sie nicht im Code definieren. Diese werden als triviale Ereignisse bezeichnet. In vielen Fällen ist nur ein triviales Ereignis erforderlich.  
  
 Sie können benutzerdefinierte Hinzufügen-, Entfernen- und Auslösen-Methoden für ein Ereignis angeben, wenn Sie benutzerdefinierte Logik als Reaktion auf das Hinzufügen oder Entfernen von Abonnenten ausführen müssen. Wenn Sie beispielsweise über ein teures Objekt verfügen, das nur für die Ereignisberichterstellung erforderlich ist, können Sie die Erstellung des Objekts verzögern, bis ein Client tatsächlich das Ereignis abonniert.  
  
 Im nächsten Beispiel wird veranschaulicht, wie Sie benutzerdefinierte Hinzufügen-, Entfernen- und Auslösen-Methoden zu einem Ereignis hinzufügen können.  
  
 [!code-cpp[cx_events#03](../cppcx/codesnippet/CPP/cx_events/class1.h#03)]  
  
## <a name="removing-an-event-handler-from-the-subscriber-side"></a>Entfernen eines Ereignishandlers von der Abonnentenseite  
 In einigen wenigen Fällen möchten Sie vielleicht einen Ereignishandler für ein Ereignis entfernen, das Sie zuvor abonniert hatten. Sie möchten es beispielsweise durch einen anderen Ereignishandler ersetzen oder einige Ressourcen löschen, die durch diesen Ereignishandler gehalten werden. Um einen Handler zu entfernen, müssen Sie das von der `+=` -Operation zurückgegebene EventRegistrationToken speichern. Sie können den `-=` -Operator im Token dann verwenden, um einen Ereignishandler zu entfernen.  Allerdings kann der ursprüngliche Handler noch aufgerufen werden, nachdem er entfernt wurde. Wenn Sie beabsichtigen, einen Ereignishandler zu entfernen, erstellen Sie daher einen Memberflag und setzen Sie diesen, wenn das Ereignis entfernt wird. Aktivieren Sie dann im Ereignishandler den Flag und kehren Sie sofort zurück, wenn der Flag gesetzt wird. Das grundlegende Muster wird im nächsten Beispiel veranschaulicht.  
  
 [!code-cpp[cx_events#04](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#04)]  
  
### <a name="remarks"></a>Hinweise  
 Mehrere Handler können demselben Ereignis zugeordnet werden. Die Ereignisquelle ruft sequenziell alle Ereignishandler von dem gleichen Thread auf. Wenn ein Ereignisempfänger innerhalb der Ereignishandlermethode blockiert, blockiert den Aufruf anderer Ereignishandler für dieses Ereignis durch die Ereignisquelle.  
  
 Die Reihenfolge, in der die Ereignisquelle Ereignishandler auf Ereignisempfängern aufruft, wird nicht garantiert und unterscheidet sich von Aufruf zu Aufruf.  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Delegaten](../cppcx/delegates-c-cx.md)   
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)