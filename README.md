# ChallengeTwo---3373722
class SearchSuggestionSystem:
    def __init__(self, products):
        self.products = sorted(products)
    
    def getSuggestions(self, searchWord):
        suggestions = []
        prefix = ""
        for char in searchWord:
            prefix += char
            matched_products = []
            for product in self.products:
                if product.startswith(prefix):
                    matched_products.append(product)
                    if len(matched_products) == 3:
                        break
            suggestions.append(matched_products)
        return suggestions
