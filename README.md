# showing-the-code-snippet-for-READ-function
@app.route("/products/<int:id>", methods=["GET"])
def read_product(id):
    product = Product.find(id)
    if product:
        return jsonify(product.serialize()), 200
    return {"error": "Product not found"}, 404
