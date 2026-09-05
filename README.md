<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>代理店専用 注文フォーム</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <header>
      <h1>代理店専用 注文フォーム</h1>
      <p>ご注文内容および納品先情報を入力してください。</p>
    </header>

    <form id="orderForm">
      
      <!-- 代理店情報 -->
      <section class="form-section">
        <h2>代理店情報</h2>
        <div class="form-group">
          <label for="agencyName">氏名（個人または会社名）<span class="required">必須</span></label>
          <input type="text" id="agencyName" name="agencyName" required placeholder="例：株式会社○○ / 山田 太郎">
        </div>
        <div class="form-group">
          <label for="agencyPhone">電話番号<span class="required">必須</span></label>
          <input type="tel" id="agencyPhone" name="agencyPhone" required placeholder="例：03-1234-5678">
        </div>
      </section>

      <!-- 注文内容 -->
      <section class="form-section">
        <h2>ご注文内容</h2>
        
        <div class="item-list">
          <div class="item">
            <div class="item-info">
              <h3>GOD-CLEANER-GOLD (サロン)</h3>
            </div>
            <div class="item-quantity">
              <input type="number" id="qtySalon" name="qtySalon" min="0" value="0" class="qty-input">
              <span>台</span>
            </div>
          </div>
          
          <div class="item">
            <div class="item-info">
              <h3>GOD-CLEANER-GOLD (個人)</h3>
            </div>
            <div class="item-quantity">
              <input type="number" id="qtyPersonal" name="qtyPersonal" min="0" value="0" class="qty-input">
              <span>台</span>
            </div>
          </div>
          
          <div class="item">
            <div class="item-info">
              <h3>カートリッジ</h3>
            </div>
            <div class="item-quantity">
              <input type="number" id="qtyCartridge" name="qtyCartridge" min="0" value="0" class="qty-input">
              <span>個</span>
            </div>
          </div>
        </div>
        <div id="quantityError" class="error-message" style="display: none;">※少なくとも1つの商品を選択してください。</div>
      </section>

      <!-- 納品先情報 -->
      <section class="form-section">
        <h2>納品先情報</h2>
        <div class="delivery-options">
          <label class="radio-label">
            <input type="radio" name="deliveryType" value="貴社納品" checked>
            <span>貴社納品（代理店様へお届け）</span>
          </label>
          <label class="radio-label">
            <input type="radio" name="deliveryType" value="直送">
            <span>直送（お客様へお届け）</span>
          </label>
        </div>

        <!-- 直送先入力エリア（デフォルト非表示） -->
        <div id="directDeliveryArea" class="hidden-area" style="display: none;">
          <h3>直送先情報</h3>
          <div class="form-group">
            <label for="directName">宛名<span class="required">必須</span></label>
            <input type="text" id="directName" name="directName" placeholder="例：顧客 太郎">
          </div>
          <div class="form-group">
            <label for="directPhone">電話番号<span class="required">必須</span></label>
            <input type="tel" id="directPhone" name="directPhone" placeholder="例：090-1234-5678">
          </div>
          <div class="form-group">
            <label for="directAddress">住所<span class="required">必須</span></label>
            <input type="text" id="directAddress" name="directAddress" placeholder="例：東京都渋谷区...">
          </div>
        </div>
      </section>

      <div class="form-actions">
        <button type="submit" id="submitBtn" class="btn-primary">注文を確定する</button>
      </div>
      <div id="formStatus" class="form-status"></div>
    </form>
  </div>
  <script src="script.js"></script>
</body>
</html>
