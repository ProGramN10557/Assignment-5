public abstract class DessertItem {
    private String name;
    public DessertItem() {
    }
    public DessertItem(String name) {
        this.name = name;
    }

    public final String getName() {
        return name;
    }

    public abstract int getCost();
}
    public class DessertShoppe {
    public static final double TAX_RATE = 4.5;
    public static final String storeName = "Dessert Shoppe and Store";
    public int maximumSizeOfItemName = 100;
    public int widthOfCost = 9;

        public static String dollarsCents(int cent) {
        StringBuilder sb = new StringBuilder();
        int BeforeDecimal = cent / 100;
        int AfterDecimal = cent % 100;
        sb.append(BeforeDecimal <= 0? "" : BeforeDecimal);
        sb.append(".");
        sb.append(AfterDecimal < 10? "0" + AfterDecimal: AfterDecimal);
        return new String(sb);
    }
}

    public class Candy extends DessertItem {
    private double pound;
    private int pricePound;
    public Candy(String name, double pound, int pricePound) {
        super(name);
        this.pound = pound;
        this.pricePerPound = pricePound;
    }

        public int getPricePound() {
        return pricePound;
    }

    public double getPound() {
        return pound;
    }
}

    public class Cookie extends DessertItem {
    private int number;
    private int priceDozen;

        public Cookie(String name, int number, int priceDozen) {
        super(name);
        this.number = number;
        this.pricePerDozen = priceDozen;
    }

        public int getCost() {
        int cost = number * priceDozen / 12;
        return (int) Math.round(cost);
    }

        public int getNumber() {
        return number;
    }

        public int getPriceDozen() {
        return priceDozen;
    }
}
    public class IceCream extends DessertItem {
    private int cost;
    public IceCream(String name, int cost) {
        super(name);
        this.cost = cost;
    }

    }
   public class Sundae extends IceCream {
    private String NameOfTopping;
    private int CostTopping;

        public Sundae( String NameOfTopping, int CostTopping) {
        this.NameOfTopping = NameOfTopping;
        this.CostTopping = CostTopping;
    }


        Public String getNameOfTopping() {
        return toppingName;
    }
}

    public class Checkout {
    private Vector<DessertItem> lists;
    private final double taxRate;

        public Checkout() {
        lists = new Vector<>();
        taxRate = DessertShoppe.TAX_RATE;
    }

        public int numberOfItems() {
        return lists.size();
    }

        public void enterItem(DessertItem item) {
        lists.add(item);
    }

        public void clear() {
        lists.clear();
    }



