---
title: Tipos de elemento de modelo UML | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML API, types
ms.assetid: 25345a53-7246-4eb7-8ad9-0b695aa171a2
caps.latest.revision: 10
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 5b8cb26c6e3d6cd51d087454d0b0c0700c1793db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476168"
---
# <a name="uml-model-element-types"></a>Tipos de elemento de modelo UML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

A versão mais recente deste tópico pode ser encontrada em [tipos de elemento de modelo UML](https://docs.microsoft.com/visualstudio/modeling/uml-model-element-types).  
  
Você pode ler e manipular um modelo UML por meio de uma interface de programação. Este tópico resume a hierarquia de tipos de elementos. A hierarquia é o mesmo que o definido na especificação de UML.  
  
 Os detalhes de cada tipo são fornecidos no [referência de API para extensibilidade de modelagem UML](../modeling/api-reference-for-uml-modeling-extensibility.md).  
  
## <a name="element-types"></a>Tipos de elemento  
 Esse é o conjunto de tipos definidos no assembly `Microsoft.VisualStudio.Uml.Interfaces.dll`.  
  
 O nome totalmente qualificado de cada item é "`Microsoft.VisualStudio.Uml.`" seguido do nome listado.  
  
 Para sua conveniência, essa lista é propus como uma hierarquia de herança. Sempre que um tipo tem mais de um supertipo, supertipos adicionais são listados após dois-pontos (:).  
  
```  
  
Classes.IElement  
|  Activities.IActivityGroup  
|  Classes.IComment  
|  Classes.IMultiplicityElement  
|  |  CompositeStructures.IConnectorEnd  
|  Classes.INamedElement  
|  |  Deployments.IDeployedArtifact  
|  |  Deployments.IDeploymentTarget  
|  |  |  Classes.IInstanceSpecification  
             : Deployments.IDeployedArtifact,  
               Deployments.IDeploymentTarget  
|  |  |  |  Classes.IEnumerationLiteral  
|  |  Interactions.IInteractionFragment  
|  |  |  Interactions.ICombinedFragment  
|  |  |  |  Interactions.IConsiderIgnoreFragment  
|  |  |  Interactions.IExecutionSpecification  
|  |  |  |  Interactions.IActionExecutionSpecification  
|  |  |  |  Interactions.IBehaviorExecutionSpecification  
|  |  |  Interactions.IInteraction  : CommonBehaviors.IBehavior  
|  |  |  Interactions.IInteractionOperand : Classes.INamespace  
|  |  |  Interactions.IInteractionUse  
|  |  |  Interactions.IOccurrenceSpecification  
|  |  |  |  Interactions.IExecutionOccurrenceSpecification  
|  |  |  |  Interactions.IMessageOccurrenceSpecification  
                   : Interactions.IMessageEnd  
|  |  |  |  |  Interactions.ILostFoundTarget  
|  |  |  |  Interactions.IOperandOccurrenceSpecification  
|  |  |  Interactions.IStateInvariant  
|  |  Interactions.ILifeline  
|  |  Interactions.IMessage  
|  |  Interactions.IMessageEnd  
|  |  Classes.INamespace  
|  |  |  Classes.IPackage  
             : Classes.IPackageableElement,  
              AuxiliaryConstructs.ITemplateableElement  
|  |  |  |  AuxiliaryConstructs.IModel  
|  |  |  Activities.IState  
|  |  Classes.IPackageableElement        
                   : AuxiliaryConstructs.IParameterableElement  
|  |  |  Classes.IConstraint  
|  |  |  |  Interactions.IInteractionConstraint  
|  |  |  CommonBehaviors.IEvent  
|  |  |  |  Interactions.IExecutionEvent  
|  |  |  |  CommonBehaviors.IMessageEvent  
|  |  |  |  |  CommonBehaviors.ICallEvent  
|  |  |  |  |  Interactions.IReceiveOperationEvent  
|  |  |  |  |  Interactions.IReceiveSignalEvent  
|  |  |  |  |  Interactions.ISendOperationEvent  
|  |  |  |  |  Interactions.ISendSignalEvent  
|  |  |  Classes.IType  
|  |  |  |  Classes.IClassifier : Classes.INamespace, Classes.IRedefinableElement, AuxiliaryConstructs.ITemplateableElement  
|  |  |  |  |  Deployments.IArtifact  
                   : Deployments.IDeployedArtifact  
|  |  |  |  |  |  Deployments.IDeploymentSpecification  
|  |  |  |  |  CommonBehaviors.IBehavioredClassifier  
|  |  |  |  |  |  UseCases.IActor  
|  |  |  |  |  |  Classes.IClass        
                         : CompositeStructures.IEncapsulatedClassifier  
|  |  |  |  |  |  |  CommonBehaviors.IBehavior  
|  |  |  |  |  |  |  |  Activities.IActivity  
|  |  |  |  |  |  |  Components.IComponent  
|  |  |  |  |  |  |  |  UseCases.ISubsystem  
|  |  |  |  |  |  |  Deployments.INode : IDeploymentTarget  
|  |  |  |  |  |  |  |  Deployments.IDevice  
|  |  |  |  |  |  |  |  Deployments.IExecutionEnvironment  
|  |  |  |  |  |  UseCases.IUseCase  
|  |  |  |  |  Classes.IDataType  
|  |  |  |  |  |  Classes.IEnumeration  
|  |  |  |  |  |  Classes.IPrimitiveType  
|  |  |  |  |  Classes.IInterface  
|  |  |  |  |  CompositeStructures.IStructuredClassifier  
|  |  |  |  |  |  CompositeStructures.IEncapsulatedClassifier  
|  |  |  Classes.IValueSpecification : Classes.ITypedElement  
|  |  |  |  Classes.IExpression  
|  |  |  |  Classes.IInstanceValue  
|  |  |  |  Classes.ILiteralSpecification  
|  |  |  |  |  Classes.ILiteralBoolean  
|  |  |  |  |  Classes.ILiteralInteger  
|  |  |  |  |  Classes.ILiteralNull  
|  |  |  |  |  Classes.ILiteralString  
|  |  |  |  |  Classes.ILiteralUnlimitedNatural  
|  |  |  |  Classes.IOpaqueExpression  
|  |  Classes.IRedefinableElement  
|  |  |  Activities.IActivityNode  
|  |  |  |  Activities.IControlNode  
|  |  |  |  |  Activities.IDecisionNode  
|  |  |  |  |  Activities.IFinalNode  
|  |  |  |  |  |  Activities.IActivityFinalNode  
|  |  |  |  |  Activities.IForkNode  
|  |  |  |  |  Activities.IInitialNode  
|  |  |  |  |  Activities.IJoinNode  
|  |  |  |  |  Activities.IMergeNode  
|  |  |  |  Activities.IExecutableNode  
|  |  |  |  |  Actions.IAction  
|  |  |  |  |  |  Actions.IAcceptEventAction  
|  |  |  |  |  |  Actions.ICreateObjectAction  
|  |  |  |  |  |  Actions.IInvocationAction  
|  |  |  |  |  |  |  Actions.ICallAction  
|  |  |  |  |  |  |  |  Actions.ICallBehaviorAction  
|  |  |  |  |  |  |  |  Actions.ICallOperationAction  
|  |  |  |  |  |  |  Actions.ISendSignalAction  
|  |  |  |  |  |  Actions.IOpaqueAction  
|  |  |  |  Activities.IObjectNode  : Classes.ITypedElement  
|  |  |  |  |  Activities.IActivityParameterNode  
|  |  |  |  |  Actions.IPin : Classes.IMultiplicityElement  
|  |  |  |  |  |  Actions.IInputPin  
|  |  |  |  |  |  Actions.IOutputPin  
|  |  |  UseCases.IExtensionPoint  
|  |  |  Classes.IFeature  
|  |  |  |  Classes.IBehavioralFeature  : Classes.INamespace  
|  |  |  |  |  Classes.IOperation  
                   : AuxiliaryConstructs.ITemplateableElement,  
                   AuxiliaryConstructs.IParameterableElement  
|  |  |  |  Classes.IStructuralFeature  
              : Classes.IMultiplicityElement,   
                Classes.ITypedElement  
|  |  |  |  |  Classes.IProperty  
                   : AuxiliaryConstructs.ITemplateableElement,   
                   CompositeStructures.IConnectableElement,   
                   Deployments.IDeploymentTarget  
|  |  |  |  |  |  CompositeStructures.IPort  
|  |  Classes.ITypedElement  
|  |  |  CompositeStructures.IConnectableElement  
             : AuxiliaryConstructs.IParameterableElement  
|  |  |  Classes.IParameter  : Classes.IMultiplicityElement, CompositeStructures.IConnectableElement  
|  AuxiliaryConstructs.IParameterableElement  
|  Classes.IProfileInstance  
  
|  Classes.IRelationship  
|  |  Activities.IActivityEdge : Classes.IRedefinableElement  
|  |  |  Activities.IControlFlow  
|  |  |  Activities.IObjectFlow  
|  |  Classes.IAssociation : IClassifier  
|  |  |  Deployments.ICommunicationPath  
|  |  CompositeStructures.IConnector  
|  |  Classes.IDirectedRelationship  
|  |  |  Classes.IDependency : Classes.IPackageableElement  
|  |  |  |  Classes.IAbstraction  
|  |  |  |  |  Deployments.IManifestation  
|  |  |  |  |  Classes.IRealization  
|  |  |  |  |  |  Classes.IInterfaceRealization  
|  |  |  |  Deployments.IDeployment  
|  |  |  |  Classes.IUsage  
|  |  |  UseCases.IExtend : Classes.INamedElement  
|  |  |  Classes.IGeneralization  
|  |  |  UseCases.IInclude : Classes.INamedElement  
|  |  |  Classes.IPackageImport  
|  |  |  AuxiliaryConstructs.ITemplateBinding  
|  Classes.IStereotypeInstance  
|  Classes.IStereotypePropertyInstance  
|  AuxiliaryConstructs.ITemplateableElement  
|  AuxiliaryConstructs.ITemplateParameter  
|  |  AuxiliaryConstructs.IClassifierTemplateParameter  
|  |  AuxiliaryConstructs.IOperationTemplateParameter  
|  AuxiliaryConstructs.ITemplateParameterSubstitution  
|  AuxiliaryConstructs.ITemplateSignature  
|  |  AuxiliaryConstructs.IRedefinableTemplateSignature   
             : Classes.IRedefinableElement  
```  
  
## <a name="see-also"></a>Consulte também  
 [Definir um perfil para estender UML](../modeling/define-a-profile-to-extend-uml.md)   
 [Definir restrições de validação para modelos UML](../modeling/define-validation-constraints-for-uml-models.md)   
 [Referência de API para extensibilidade de modelagem UML](../modeling/api-reference-for-uml-modeling-extensibility.md)



