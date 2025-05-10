Random rnd = new Random();
string onaykodu;

private void Onayla_Click(object sender, EventArgs e)
{
    onaykodu = rnd.Next(100, 999).ToString();
    MailMessage mail = new MailMessage("karaalperen059.1@gmail.com", textBox3.Text, "GÜVENLİ KOD DOĞRULAMASI İÇİN KOD", "Güvenlik Doğrulama Kodu : "+onaykodu);
    SmtpClient smtp = new SmtpClient("smtp.live.com", 587);
    smtp.EnableSsl = true;
    smtp.Credentials = new NetworkCredential(textBox3.Text,textBox4.Text);
    
    smtp.Send(mail);
    MessageBox.Show("Mail Gönderildi...");
}
