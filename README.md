# Builder-Pattern-Assignment
```
public class Pizza {
    private String crust;
    private String sauce;
    private List<String> toppings;

    public static class Builder {
        private String crust;
        private String sauce;
        private List<String> toppings = new ArrayList<>();

        public Builder(String crust, String sauce) {
            this.crust = crust;
            this.sauce = sauce;
        }

        public Builder addTopping(String topping) {
            toppings.add(topping);
            return this;
        }

        public Pizza build() {
            return new Pizza(this);
        }
    }

    private Pizza(Builder builder) {
        crust = builder.crust;
        sauce = builder.sauce;
        toppings = builder.toppings;
    }

}


\\In this example, the `Pizza` class has a nested `Builder` class that allows for easy creation of `Pizza` objects with different combinations of toppings. The  \\`Builder` class has methods for setting the crust and sauce, as well as adding toppings one by one. Finally, the `build()` method creates a new `Pizza` object with \\all the specified properties.

To create a new pizza object using the builder pattern, we can do something like this:


Pizza pizza = new Pizza.Builder("thin", "tomato")
                .addTopping("cheese")
                .addTopping("mushrooms")
                .addTopping("olives")
                .build();
 
