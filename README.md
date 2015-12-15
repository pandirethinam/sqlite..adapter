public class DataAdapter extends ArrayAdapter {
    List< Contact> contacts
            ;

    Context context;

    Contact contact;

    public DataAdapter(Context context, int resource, List objects) {
        super(context, resource, objects);
        this.contacts=objects;
        this.context=context;

    }

    public View getView(int position,View view,ViewGroup parent) {
        LayoutInflater inflater= (LayoutInflater) context.getSystemService(context.LAYOUT_INFLATER_SERVICE);
        View rowView=inflater.inflate(R.layout.datalist, null,true);
        //  TextView txtTitle=(TextView) rowView.findViewById(R.id.name1);
        TextView txt1= (TextView) rowView.findViewById(R.id.id1);
        TextView txt2= (TextView) rowView.findViewById(R.id.nm);
        TextView txt3= (TextView) rowView.findViewById(R.id.pn);


        // itemBean=resultValues.get(position);

        contact=contacts.get(position);

        //  txtTitle.setText(itemBean.getPersonnalname());
        //txt1.setText(contact.getID());
        txt2.setText(contact.getName());
        txt3.setText(contact.getPhoneNumber());

        //.setText(String.valueOf(itemBean.getYear()));

        return rowView;

    };
}
