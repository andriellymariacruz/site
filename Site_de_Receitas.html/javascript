let cart = [];

function addToCart(productName, price) {
    cart.push({ name: productName, price: price });
    updateCart();
    alert(`${productName} adicionado ao carrinho!`);
}

function updateCart() {
    const cartItemsDiv = document.getElementById('cartItems');
    const cartTotalSpan = document.getElementById('cartTotal');
    
    cartItemsDiv.innerHTML = '';
    let total = 0;
    
    cart.forEach((item, index) => {
        const itemDiv = document.createElement('div');
        itemDiv.className = 'cart-item';
        itemDiv.innerHTML = `
            <span>${item.name}</span>
            <div>
                <span>R$ ${item.price.toFixed(2)}</span>
                <button onclick="removeFromCart(${index})" style="margin-left: 1rem; background: #ff4444; border: none; color: white; padding: 0.2rem 0.5rem; border-radius: 3px; cursor: pointer;">Remover</button>
            </div>
        `;
        cartItemsDiv.appendChild(itemDiv);
        total += item.price;
    });
    
    cartTotalSpan.textContent = total.toFixed(2);
}

function removeFromCart(index) {
    cart.splice(index, 1);
    updateCart();
}

function toggleCart() {
    const modal = document.getElementById('cartModal');
    if (modal.style.display === 'block') {
        modal.style.display = 'none';
    } else {
        modal.style.display = 'block';
    }
}

function checkout() {
    if (cart.length === 0) {
        alert('Seu carrinho está vazio!');
        return;
    }
    const total = cart.reduce((sum, item) => sum + item.price, 0);
    const message = `Olá! Gostaria de fazer um pedido.\n\nProdutos:\n${cart.map(item => `- ${item.name}: R$ ${item.price.toFixed(2)}`).join('\n')}\n\nTotal: R$ ${total.toFixed(2)}`;
    window.open(`https://wa.me/5584996418357?text=${encodeURIComponent(message)}`, '_blank');
}
