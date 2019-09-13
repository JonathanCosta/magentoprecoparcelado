# magentoprecoparcelado
Módulo Preço Parcelado para Magento

Preço Parcelado

Com esta extensão é possível você mostrar o preço parcelado do seu produto. Através do painel de administração é possível configurar os modos de exibição (tabela de parcelas ou em texto específico), número de meses, valor do juros, parcela mínima, entre outros.

COMO EXIBIR O TEXTO DE PARCELA:

```php
if (isset($modulesArray['FranciscoPrado_PrecoParcelado'])) { ?>
	<div class="payment-form">
	    <p class="m-0 d-block">
	    	<strong>
				<?php echo Mage::helper('franciscoprado_precoparcelado')->getSinglePrice($this->getProduct()->getFinalPrice()); ?>
	    	</strong> 
	    	à vista no boleto
	    </p>
	    <p class="m-0 d-block">
	    	ou
	    	<strong>
				<?php echo Mage::helper('franciscoprado_precoparcelado')->getPrice($this->getProduct()->getFinalPrice()); ?>
	    	</strong> 
	    	sem juros!
	    </p>
	</div>	
<?php } ?>
```

Suponhamos que você queira exibir, abaixo do preço à vista do produto, a forma em parcelas do tipo "ou em 12x de R$ 10,00". Para isso basta você adicionar o seguinte código ao arquivo app/design/frontend/base/default/template/catalog/product/price.phtml:


Onde "$this->getProduct()->getFinalPrice()" é o parâmetro do preço. Este modo foi escolhido por ser mais "aberto": muitas pessoas podem preferir colocar esse texto em outras áreas (como embaixo do botão "Comprar", entre outras.)

CONFIGURAÇÕES:

Para alterar configurações do módulo, vá em Sistema | Configuração | Vendas
