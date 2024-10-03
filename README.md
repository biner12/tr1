import streamlit as st
import requests
from streamlit_lottie import st_lottie


#Page title
st.set_page_config(
    page_title ="Construction Cost Estimation",
    page_icon="🏗️",
 )
#---------------------------------------------

def calculate_construction_cost(area, num_floors, num_rooms, num_bathrooms):
    cost_per_sqm = 50000

    total_area = area * num_floors
    total_cost = total_area * cost_per_sqm + num_rooms * 100000 + num_bathrooms * 75000

    return total_cost
def calculate_total_cost2( professional_fees, machinery_cost, permit_cost):
    total_cost2 = professional_fees + machinery_cost + permit_cost
    return total_cost2

def total_expenses(total_cost2, total_cost):
    overall=total_cost2 + total_cost
    return overall

#----------------------------------------------

#Navigation menu(sidebar)


st.sidebar.title("🏗️ CEstimate 🏗️")
st.sidebar.write("Welcome to the CEstimate!")

st.sidebar.title("Parameters")
st.sidebar.write("This tool accounts for the following parameters:")

st.sidebar.subheader("Accuracy")
st.sidebar.write("The tool provides an accurate estimate of the total construction project cost, but not the exact amount.")

st.sidebar.subheader("Cost Components")
st.sidebar.write("The tool includes the cost of construction materials, professional fees, machinery, and building permits.")

st.sidebar.subheader("Cost Variations")
st.sidebar.write("The cost of construction materials and labor varies with time and location, resulting in variations in the estimated cost.")

st.sidebar.subheader("Building Classification")
st.sidebar.write("The estimation of construction cost differs based on the classifications of building construction.")

#PAGES
st.sidebar.header ("Use the options below to navigate our site!")
menu = ["Home", "Estimation", "About", "FAQS", "Feedback", "User"]
choice = st.sidebar.selectbox("Select a page", menu)

st.sidebar.header("Inquiries? Contact us through:")
st.sidebar.write("📧Email : cestimate.tech@gmail.com")
st.sidebar.write("📞Phone # : +639754038129")
st.sidebar.write("☎️Landline : 412 - 3576")
st.sidebar.write("👍Facebook Page: CE-stimate")
st.sidebar.write("🐦Twitter: @CEstimate")
#HOME PAGE
if choice == "Home":
    st.title("🏗️ CEstimate: Reliable Construction Cost Estimation Tool for Civil Engineers 🏗️")
    # animations
    def load_lottieurl(url: str):
        r = requests.get(url)
        if r.status_code != 200:
            return None
        return r.json()
    lottie_hello = load_lottieurl("https://assets10.lottiefiles.com/packages/lf20_9ye8w8M9JF.json")
    st_lottie(
        lottie_hello,
        speed=1,
        reverse=False,
        loop=True,
        quality="high",
        height=400,
        width=650,
    )
    st.write(
        "This tool will help you estimate the construction cost of your project based on various parameters. Construction cost estimation is an "
        "important process that involves calculating the total cost of a construction project, including materials, labor, equipment, and other expenses. "
        "With this tool, you can get a rough estimate of how much your construction project will cost, which can help you plan your budget and make informed "
        "decisions about the project.")

    st.title ("Featured Projects")
    st.header ("ROMULUS")
    st.write ("This breathtaking fusion of open and private areas redefines contemporary design. In this design, there are three roomy bedrooms, three bathrooms, "
              "an alfresco, a living room, a huge kitchen, and a rumpus room. Absolutely, this is a striking design with elegant and sophisticated exterior concepts that is "
              "suitable for a big, expanding family.")
    image_url = ('https://scontent.fmnl15-1.fna.fbcdn.net/v/t1.15752-9/343920284_1067696810863038_13892978914050455_n.webp?stp=dst-webp&_nc_cat=102&ccb=1-7&_nc_sid=ae9488&_nc_ohc=bpn55govP4sAX8UgKvo&_nc_ht=scontent.fmnl15-1.fna&oh=03_AdQlgS0h5f5hCu1D5qyNwug_--TQYqjaY6VS4CEdzT1D-w&oe=6479C36F')
    st.image(image_url, caption='Romulus', width=500)
    st.write("House Plan Details:")
    st.write("Two storey")
    st.write("Beds: 4")
    st.write("Baths: 3")
    st.write("Floor Area: 145 sq.m.")
    st.write("Cost: 12,600,000 PHP")

    st.header("FRANCO")
    st.write ("The combination of warm and soft hues gives the blend of cream, grey, and brown colors a beautiful facade.")
    image_url = ("https://scontent.fmnl15-1.fna.fbcdn.net/v/t1.15752-9/344297647_789997062748813_1321151727240577795_n.jpg?_nc_cat=109&ccb=1-7&_nc_sid=ae9488&_nc_ohc=wJeQR9J4ePoAX-2uVZz&_nc_ht=scontent.fmnl15-1.fna&oh=03_AdRvpeHc3v1Tl6XZvR3iqTXL17f_JyJJVhKggjcG9jt8ug&oe=6479BF85")
    st.image(image_url, caption='Franco', width=500)
    st.write("House Plan Details:")
    st.write("Two storey")
    st.write("Beds: 4")
    st.write("Baths: 3")
    st.write("Floor Area: 190 sq.m")
    st.write("Cost: 17,500,000 PHP")

    st.header ("EMMA")
    st.write ("The house features an excellent design that saves space without seeming crowded. The house includes a number of utilitarian features that made it even more liveable and functional. White walls are made even more attractive due to the presence of white stones and translucent stones on top of them. ")
    image_url = ("https://scontent.fmnl15-1.fna.fbcdn.net/v/t1.15752-9/309871216_429308782696349_7298202543992176782_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=ae9488&_nc_ohc=nG-0s2FfJuQAX9lsws7&_nc_ht=scontent.fmnl15-1.fna&oh=03_AdSWVC2Cx-Njk2WVE5LT3NKcAfd5qEOK2enql86hNCzSaw&oe=6479D829")
    st.image(image_url, caption='Emma', width=500)
    st.write("House Plan Details:")
    st.write("Two storey")
    st.write("Beds: 4")
    st.write("Baths: 3")
    st.write("Floor Area: 175 sq.m.")
    st.write("Cost: 15,840,000 PHP")



#CALCULATOR PAGE
elif choice == "Estimation":

    st.title(" 🧮 Let's calculate! 🧮")
    # animations
    def load_lottieurl(url: str):
        r = requests.get(url)
        if r.status_code != 200:
            return None
        return r.json()


    lottie_hello = load_lottieurl("https://assets6.lottiefiles.com/packages/lf20_fw6euzap.json")
    st_lottie(
        lottie_hello,
        speed=1,
        reverse=False,
        loop=True,
        quality="high",
        height=600,
        width=700,
    )

    st.header("Enter the following parameters to estimate the construction cost:")

    area = st.number_input("Area (in square meters):", min_value=0.0)
    num_floors = st.number_input("Number of floors:", min_value=0)
    num_rooms = st.number_input("Number of rooms:", min_value=0, format="%d")
    num_bathrooms = st.number_input("Number of bathrooms:", min_value=0, format="%d")
    professional_fees = st.number_input("Professional Fees:", value=0.0, step=1000.0)
    machinery_cost = st.number_input("Machinery Cost:", value=0.0, step=1000.0)
    permit_cost = st.number_input("Building Permit Cost:", value=0.0, step=1000.0)

    cement = area * 10 #Kg
    steel = area * 4 #Kg
    aggregate = area * 0.6 #Tons
    paint = area * 0.5 #Liters
    flooring = area * num_floors #Sq. Meters

    summary = {"Cement (kg)": cement,
               "Steel (kg)": steel,
               "Aggregate (tons)": aggregate,
               "Paint (Liters)": paint,
               "Flooring (Square meters)": flooring
               }

    #Calculate construction cost based on inputs
    total_cost = calculate_construction_cost(area, num_floors, num_rooms, num_bathrooms)
    total_cost2 = calculate_total_cost2( professional_fees, machinery_cost, permit_cost)
    overall = total_expenses(total_cost2, total_cost)

    #Display construction cost
    st.header("Results:")
    if st.button("Calculate"):
        st.write("Based on the inputs you provided, the estimated construction cost is:")
        st.title(f"PHP {overall:,.2f}")
        st.write("Hypothetically, you will be needing:")
        for key, value in summary.items():
            st.write(f"- {key}: {value}")
        st.write("Which costs:")
        st.title(f"PHP {total_cost:,.2f}")
        #Total
        if total_cost == 0:
            st.write("Hmm, it looks like you haven't entered any parameters yet.")
        elif total_cost < 1000000:
            st.write("Wow, that's a great deal! Your construction cost estimate is very affordable.")
        elif total_cost < 2000000:
            st.write("Your construction cost estimate is reasonable and fits within the average budget for most people.")
        elif total_cost < 5000000:
            st.write("Your construction cost estimate is a bit high, but still within the range of what many people spend.")
        else:
            st.write(
                "Your construction cost estimate is very high. You must be rich!")
    if st.button("Save"):
        content = f"Construction Cost Estimate:\nEstimated Cost: PHP {overall:,.2f}\n\nHypothetically, you will be needing:\n"
        for key, value in summary.items():
            content += f"- {key}: {value}\n"
        content += f"\nWhich costs: PHP {total_cost:,.2f}"
        #file download link
        st.download_button(label="Download Estimate", data=content, file_name="construction_estimate.txt", mime="text/plain")

#ABOUT PAGE
elif choice == "About":
    st.title ("💖 ABOUT US 💖")
    def load_lottieurl(url: str):
        r = requests.get(url)
        if r.status_code != 200:
            return None
        return r.json()
    lottie_hello = load_lottieurl("https://assets5.lottiefiles.com/packages/lf20_v1yudlrx.json")
    st_lottie(
        lottie_hello,
        speed=1,
        reverse=False,
        loop=True,
        quality="high",
        height=650,
        width=650,
    )
    st.title  ("✨GOAL:")
    st.write  ("To revolutionize the construction industry by making cost estimation more accessible, precise, and profitable.")

    st.title  ("✨MISSION:")
    st.write  ("To simplify and optimize the cost estimation process for Civil Engineering construction by providing a reliable "
              "and efficient tool for accurately projecting project costs.")

    st.title  ("✨VISION:")
    st.write  ("To be the go-to online platform for construction cost estimation, continuously innovating and improving our platform "
             "with the most advanced technology and exceptional customer service to our users.")

    st.title  ("✨VALUES:")
    st.header  ("Reliability ")
    st.write ("We are committed to providing cost estimation tools that are accurate and dependable.")

    st.header  ("Efficiency  ")
    st.write ("We intend on simplifying the construction cost estimation process for our users, making it faster and more efficient.")

    st.header  ( "Transparency ")
    st.write ("We adhere to the highest standards of transparency and ethics in all our operations, ensuring that our customers can "
             "rely on our platform.")

    st.header  ("Innovation ")
    st.write ("We are constantly striving to improve our platform through cutting-edge technology and innovative solutions.")

    st.header  ("Customer Focus ")
    st.write ("We prioritize our customers' needs, offering exceptional customer service and tailored solutions to meet "
             "their requirements.")



#FAQS PAGE
elif choice == "FAQS":
    st.title ("FAQS")
    st.write ("Get quick answers to a variety of questions on cost and quantity take-offs")


    def load_lottieurl(url: str):
        r = requests.get(url)
        if r.status_code != 200:
            return None
        return r.json()


    lottie_hello = load_lottieurl("https://assets8.lottiefiles.com/packages/lf20_eqNmg0L9I9.json")
    st_lottie(
        lottie_hello,
        speed=1,
        reverse=False,
        loop=True,
        quality="high",
        height=300,
        width=650,
    )

    st.header ("01  What exactly is a construction cost estimation tool and how can it assist me with my project?")
    st.write ("A construction cost estimation tool is an online application that helps users in estimating the cost "
              "of their construction projects based on different input variables. By using this tool, you can gain an "
              "initial understanding of your project's potential cost, saving you time and money")

    st.header ("02 How accurate are the estimates generated by this tool?")
    st.write ("The quality and completeness of the data you provide determines the accuracy of the estimates. Our tool "
              "calculates estimated costs using cutting-edge technology and industry standards, but it is important to "
              "keep in mind that there could be unforeseeable circumstances or factors that may influence the final cost.")

    st.header ("03 What types of construction projects can I use this tool for?")
    st.write ("Our construction cost estimation tool can be used for a wide range of projects, such as new construction, "
              "remodeling, renovations, additions, and repairs.")

    st.header ("04 Is there a fee to use this tool or is it free?")
    st.write ("Our construction cost estimation tool is completely free to use. You can access it anytime, anywhere, and "
              "as many times as you need.")

    st.header ("05 How do I estimate my construction costs using this tool?")
    st.write ("Using our tool is easy and straightforward. Simply enter the necessary data and the tool will generate an "
              "estimated cost for you. You can adjust the inputs as necessary to get a more accurate estimate.")

    st.header ("06 Can I save or print my estimates for future reference?")
    st.write ("Yes, you can save your estimates and print them out for future reference. Once you have generated the estimate,"
              " simply click on the 'Save' or 'Print' buttonand the tool will generate a PDF file for you to download or print.")

    st.header ("07 What should I do if I have questions or issues while using the tool?")
    st.write ("If you have any questions or issues while using our construction cost estimation tool, please contact our support "
              "team at cestimate.tech@gmail.com. We are always availble to assist you and provide you with the information you need.")

#FEEDBACK PAGE

elif choice == "Feedback":
    st.title ("Feedback Page")
    def load_lottieurl(url: str):
        r = requests.get(url)
        if r.status_code != 200:
            return None
        return r.json()


    lottie_hello = load_lottieurl("https://assets2.lottiefiles.com/private_files/lf30_VeGYYQ.json")
    st_lottie(
        lottie_hello,
        speed=1,
        reverse=False,
        loop=True,
        quality="high",
        height=450,
        width=700,
    )
    feedback = st.text_area("Your Feedback")
    rating = st.slider("⭐️Rate the Application (1-5)⭐️", 1, 5)
    if st.button("Submit Feedback"):
        if rating == 5:
            st.write("We're thrilled to hear that you loved our application! Thank you for the 5-star rating!⭐️⭐️⭐⭐️⭐️")
        elif rating == 4:
            st.write("Thank you for the positive feedback! We appreciate the 4-star rating! ⭐️⭐️⭐️⭐️️")
        elif rating == 3:
            st.write("Thank you for your feedback. We'll use it to improve our application.⭐️⭐️⭐️")
        elif rating == 2:
            st.write("We're sorry to hear that you didn't have the best experience. We appreciate your feedback.⭐️⭐️")
        elif rating == 1:
            st.write(
                "We apologize for any inconvenience caused. We'll take your feedback into consideration for future improvements.⭐️")

elif choice == "User":

    select = st.selectbox('Login/Signup', ['Login', 'Signup'])
    if select == 'Login':

        email = st.text_input('Email Address')
        password = st.text_input('Password', type='password')
        st.success("Login successful!")
        redirect_url = "http://localhost:8501"  # Modify the URL to your Streamlit app
        st.markdown(f'<a href="{redirect_url}" target="_blank">Click here to redirect</a>', unsafe_allow_html=True)

    elif select == 'Signup':
        email = st.text_input('Email Address')
        password = st.text_input('Password', type='password')

        username = st.text_input('Enter your unique username')

        st.button('Create my account')
        st.success("Login successful!")
        redirect_url = "http://localhost:8501"  # Modify the URL to your Streamlit app
        st.markdown(f'<a href="{redirect_url}" target="_blank">Click here to redirect</a>', unsafe_allow_html=True)
#----

